Zilch comes with a set of templates/macros that allow your C++ classes and functions to be called by Zilch code. We recommend that you read up on the LibraryBuilder documentation first. Internally, the macros simply create a LibraryBuilder and automatically add BoundTypes, Properties, and Functions to it.

 #  Internal Binding

The first thing we need to do is create a class that derives from StaticLibrary. That class must be visible to all the places where we’re going to be doing Zilch binding (generally in a header). We can use the ZilchDeclareStaticLibrary macro to declare the entire class and singleton implementation.

Below we have an example of a header file that contains the static library Wallaby and two example classes that might belong to that library. Remember, the name of the library can be anything you want.

```lang=csharp

# pragma once

#include "Zilch.hpp"
using namespace Zilch;

ZilchDeclareStaticLibrary(Wallaby);

class Character : public IZilchObject
{
public:
  // Using internal binding we'll declare that this class should be registered with Zilch
  // This macro is only a declaration, and somewhere in a single cpp file we must use the 'ZilchDefineBaseType' macro
  // ReferenceType means it will be allocated on the heap and always referenced by handle
  ZilchDeclareBaseType(Character, TypeCopyMode::ReferenceType);

  // Various types of members we may want to bind
  Character();
  virtual ~Character();
  virtual void Speak() const;
  void Yell(float volume) const;
  void Yell() const;
  static int ComputeLives(float mana, int level);
  static const int MaxLives = 100;
  int Lives;
  float InternalHealth;
  float GetHealth() const;
  void SetHealth(float value);
};

class Player : public Character
{
public:
  // Note here that we use the 'Derived' macro to inform Zilch that Player derives from Character
  // This allows implicit casting operations in Zilch as well as dynamic down-casts
  // The TypeCopyMode of the base type is used here (ReferenceType can only inherit from ReferenceType, and so on)
  ZilchDeclareDerivedType(Player, Character);
  
  // Various types of members we may want to bind
  String Name;
  Player(const String& name, float startingHealth);
  virtual ~Player();

  // Note that we don't bind Speak again because it gets inherited from the base
  virtual void Speak() const;
};
```

With *Internal Binding* we must use the `ZilchDeclareBaseType` and `ZilchDeclareDerivedType` macros in a public section of the class (typically at the beginning, but make sure to use public!). The Character class also publicly inherits from `IZilchObject`, which is not required but allows the `character->ZilchGetDerivedType()` function to be virtual, which will retrieve the BoundType for `Player` instead of `Character`.
The following code should appear once within a translational unit (do not put this within a header):

```lang=csharp

# include "Wallaby.hpp"


ZilchDefineStaticLibrary(Wallaby)
{
  // We have to initialize all types that we have bound to our library
  // Ideally we could use pre-main or automatic registration, but there's a major issue where
  // compilers will automatically remove "unreferenced" classes, even if they are referenced
  // by globals/pre-main initializations. This method ensures that all classes will be properly bound
  ZilchInitializeType(Character);
  ZilchInitializeType(Player);
}

// This allows us to define all the members on Character (as well as which library it belongs to: Wallaby)
// The 'builder' and 'type' members are only there to let the user know they can do builder->... or type->...
ZilchDefineType(Character, "Character", Wallaby, builder, type)
{
  // The 'ZilchNoNames' macro is simply a way of saying that there are no parameter names for the argument types
  // Zilch supports named parameter calling, so feel free to provide them

  // We should generally always bind a constructor and destructor,
  // especially if this is a dervied class and the base is constructable
  ZilchBindConstructor(builder, type, Character, ZilchNoNames);
  ZilchBindDestructor(builder, type, Character);

  // The 'ZilchNoOverload' lets the binding know that there are no overloads of the same name
  // Otherwise, we'd have to pass in the type/signature of the member function in parentheses
  ZilchBindMethod(builder, type, &Character::Speak, ZilchNoOverload, "Speak", ZilchNoNames);

  // Bind both overloads of Yell
  ZilchBindMethod(builder, type, &Character::Yell, (void (Character::*)(float) const), "Speak", "volume");
  ZilchBindMethod(builder, type, &Character::Yell, (void (Character::*)() const), "Speak", ZilchNoNames);

  // The binding templates/macros can automatically determine if you're binding a static or instance member function
  // You can also bind global functions to a class
  ZilchBindMethod(builder, type, &Character::ComputeLives, ZilchNoOverload, "ComputeLives", "mana, level");

  // Zilch does not have the concept of 'const' (therefore we remove all consts from bound C++ members)
  // It is up to us to be very careful here and bind const members as 'Get' only
  ZilchBindField(builder, type, &Character::MaxLives, "MaxLives", PropertyBinding::Get);

  ZilchBindField(builder, type, &Character::Lives, "Lives", PropertyBinding::GetSet);

  // We can specially bind getters and setters in C++ as a single property in Zilch
  ZilchBindProperty(builder, type, &Character::GetHealth, &Character::SetHealth, "Health");
}

ZilchDefineType(Player, "Player", Wallaby, builder, type)
{
  // Be sure to always pass the correct types in to all the bindings
  // Do NOT pass Character, for example, and avoid copy pasting from other bindings!

  // Even though we only have a non-overloaded constructor, we unfortunately cannot
  // detect the argument types automatically for constructors due to a limitation in C++
  // The argument types must be explicitly passed in
  ZilchBindConstructor(builder, type, Player, "name, startingHealth", const String&, float);
  ZilchBindDestructor(builder, type, Player);

  ZilchBindField(builder, type, &Player::Name, "Name", PropertyBinding::GetSet);
  
  // Note that we don't bind Speak again because it gets inherited from the base
}
```

The macro `ZilchDefineStaticLibrary` is a place where we must initialize all types defined within our library. Because that list of types must exist somewhere within code, we often place that entire `ZilchDefineStaticLibrary` in its own translational unit (cpp). The macros `ZilchDefineType` can be placed all in a single file, or next to their respective class implementations (such as in a Character.cpp and Player.cpp). Be aware that placing them all in the same file encourages merge conflicts.

The parameters `builder` and `type` can be used to out

A call to `GetLibrary` will automatically build the library. If you place breakpoints or prints in the `ZilchDefineStaticLibrary` or `ZilchDefineType` macro-functions you will see the code running. GetLibrary will most likely get called when you populate dependencies:

`dependencies.push_back(Wallaby::GetLibrary());`

 #  External Binding

If you don’t want your classes to have knowledge about Zilch (for example you do not wish to include Zilch.hpp in your core class headers), you can use our External Binding macros. The external binding has one major limitation which is that you cannot call `ZilchGetDerivedType` on a C++ base class, because the function will not exist. It is possible to mix internal and external binding together, which is especially common when binding types that you cannot change the definition of.

External binding works the same as internal binding, except the following differences:

- `ZilchDeclareBaseType` and `ZilchDeclareDerivedType` become `ZilchDeclareExternalBaseType` and `ZilchDeclareExternalDerivedType`
 - Must be used outside the class definition in a place where the rest of the binding can see. Typically you declare them in a header or at the top of a translational unit that you place all of the external binding.
- `ZilchDefineType` becomes `ZilchDefineExternalType`

 #  Binding Enumerations or Flags
Since enumerations cannot be virtual or have methods declare inside of them, all enums must be bound using External Binding. At the moment, enumerations MUST be the same size as the int type, which you can generally force either be using the new C++ class enums or by making an enum value set to `0x7FFFFFFF`. Inside the `ZilchDefineExternalType` macro at the beginning use the following lines:

```lang=csharp
// You can also pass in SpecialType::Flags if all the values of the enum are bit flags
ZilchBindEnum(builder, type, SpecialType::Enumeration);
ZilchBindEnumValue(builder, type, YourEnum::ValueName, "ValueName");
```

 #  Built-in Types Available To Binding
The following list is not exhaustive, but contains the most common types that we accept in binding automatically. Technically anything defined in Zilch.hpp that either internal or external binding and is bound to the Core library can be used. Note that most primitives (int, float, etc) are simply type-defined as Integer, Real, etc and can be used in binding.

 - [ Boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown)
 - [ Boolean2](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown)
 - [ Boolean3](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown)
 - [ Boolean4](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown)
 - [ Byte](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown)
 - [ Integer](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown)
 - [ Integer2](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown)
 - [ Integer3](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown)
 - [ Integer4](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown)
 - [ Real](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown)
 - [ Real2](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown)
 - [ Real3](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown)
 - [ Real4](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown)
 - [ Quaternion](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown)
 - [ String](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown)
 - [ DoubleReal](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown)
 - [ DoubleInteger](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown)
 - [ Handle](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown) (binds to a special type that can accept any handle to any object type)
 - [ Delegate](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown) (binds to a special type that can accept any delegate)
 - [ Any](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown) (can accept any type in Zilch)
 - [ StringBuilderExtended](https://github.com/zeroengineteam/ZeroDocs/blob/master.markdown)
 - [[ | ArrayClass<Handle>]]
 - [[ | ArrayClass<Delegate>]]
 - [[ | ArrayClass<Boolean>]]
 - [[ | ArrayClass<Boolean2>]]
 - [[ | ArrayClass<Boolean3>]]
 - [[ | ArrayClass<Boolean4>]]
 - [[ | ArrayClass<Byte>]]
 - [[ | ArrayClass<Integer>]]
 - [[ | ArrayClass<Integer2>]]
 - [[ | ArrayClass<Integer3>]]
 - [[ | ArrayClass<Integer4>]]
 - [[ | ArrayClass<Real>]]
 - [[ | ArrayClass<Real2>]]
 - [[ | ArrayClass<Real3>]]
 - [[ | ArrayClass<Real4>]]
 - [[ | ArrayClass<Quaternion>]]
 - [[ | ArrayClass<DoubleInteger>]]
 - [[ | ArrayClass<DoubleReal>]]
 - [[ | ArrayClass<Any>]]

The following types are automatically redirected to the Zilch Integer type (except unsigned long long which redirects to DoubleInteger):

```lang=csharp
char
signed char
signed short
unsigned short
unsigned int
signed long
unsigned long
unsigned long long
```

 #  Limitations

At the moment, there is no way in binding to accept templates (such as HashMapClass or ArrayClass) templated upon any other type other than specified above. 

 