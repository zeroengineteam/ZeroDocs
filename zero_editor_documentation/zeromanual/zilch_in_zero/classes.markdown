Classes and structs define the type of certain objects in Zilch, and the `class` keyword can create user-defined data types.  The [Variables](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/variables_and_data_types.markdown) and [Functions](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/functions.markdown) defined in a class or struct are all stored and referenced from instantiations.  In contrast with how Structs handle [Memory Management](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/memory_management.markdown), classes are copied `by-reference`.

 # Class Contents
Classes in Zilch must be defined in [global scope](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/variables_and_data_types.markdown#global-scope).  The format for classes and structs are as shown below:

```lang=csharp, name=Simple Classes
struct SimpleStruct {}
class SimpleClass {}
```

Any members that belong to `SimpleStruct` or `SimpleClass` will be defined within their curly braces.

 ## Struct Members in Classes
Because structs are copied `by-value`, structs cannot have class members.  As shown in the code snippet below, any other permutation of containment is valid.

```lang=csharp, name=Classes and Structs in Classes and Structs
struct StructInStruct { var MyStruct : SimpleStruct; }
struct ClassInStruct { var MyClass : SimpleClass; } // ERROR
class StructInClass { var MyStruct : SimpleStruct; }
class ClassInClass { var MyClass : SimpleClass; }
```

The class `MyClass` is a member of `ClassInStruct`, which is a struct.  Having a class in a struct will cause Zilch to throw a compile-time exception.

 ## Static vs Non-Static Members
Variables and functions inside a class or struct are known as members. Most member variables must be accessed through instantiations of the object.  The one exception are member variables with the [Static](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/attributes.markdown#static) [Attribute](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/attributes.markdown).

```lang=csharp, name=Static Members
class MyClass
{
  // standard variable instantiation and initialization
  var MyReal : Real = 0;
  
  // static variable
  [Static]
  var MyStaticBoolean : Boolean = false;
  
  // static function
  [Static]
  function MyStaticFunction() {}
}
```

Accessing static members can be done with `MyVariableClass.MyStaticReal` or `MyVariableClass.MyStaticFunction`, while `MyVariableClass().MyReal` is a way of accessing a non-static member.

 ## Member Variable Declaration
Member variables define the data in a class.  The rules for defining member variables differ from how local variables are defined.

```lang=csharp, name=Member Variables
class MyClass
{
  // variable instantiation only is allowed
  var MyDoubleReal : DoubleReal;
  
  // ERROR: type deduction not allowed on member variables
  var MyBoolean = false;
}
```
Notice how `MyDoubleReal` isn't initialized.  At the class scope, uninitialized member variables will be set to the default values of their types. Also note that member variables must be explicitly typed.  `MyBoolean` is set to `false`, but Zilch will still throw a compiler error if the type is omitted.

 ## Member Functions
Member functions hold executable code, can take input parameters, and can return data.  Member functions without the `[Static]` attribute  also have access to the instantiated object that invoked them.

```lang=csharp, name=Member Functions
class MyClass
{
  var MyReal : Real = 1.2;
  
  function MyFunc()
  {
    var localReal = this.MyReal;
  }
  
  [Static]
  function MyFunc()
  {
    var localReal = this.MyReal; // ERROR
  }
}
```

Notice how `MyReal`, a member variable of `MyClass`, is accessed in `MyFunc` using the `this` keyword.  `this` refers to the instantiated object.  If the function is static, then `this` cannot be used as there is no instantiation of `MyClass`.  Also notice how there are two versions of `MyFunc`, one static and one not.  This is valid because static members must always be accessed through the class with the format `<class>.<function>`.

 ## Constructors and Destructors
Structs/Classes can have constructor and destructors, which are special functions with no return type.  Constructors are called when an object is instantiated, and the destructor is called when the object is deleted.

```lang=csharp, name=Default Constructor
class ExplicitDefault
{
  constructor() {}
}

class ImplicitDefault {}

class Driver
{
  function MyFunction()
  {
    ExplicitDefault(); // call default constructor
    ImplicitDefault(); // call default constructor (implicitly defined)
  }
}
```
The class `ExplicitDefault` has a single constructor that takes no parameters.  This constructors type is known as the //default constructor//.  Notice how the constructor is called by the class name in the statement `ExplicitDefault();`  Also notice how `ImplicitDefault` is constructed with the default constructor in the statement `ImplicitDefault();`.  As long as there are no constructors defined, the default will always be defined by zilch.

```lang=csharp, name=Custom Constructors
class ExplicitCustom
{
  constructor(r : Real) {}
}

class ExplicitCustomAndDefault
{
  constructor() {}
  constructor(r : Real) {}
}

class Driver
{
  function MyFunction()
  {
    ExplicitCustom(); // ERROR
    ExplicitCustom(1.0);
    ExplicitCustomAndDefault();
    ExplicitCustomAndDefault(1.0);
  }
}
```

The class `ExplicitCustom` defines a single constructor that takes a single [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown).  This means that `ExplicitCustom` cannot be default constructed, therefore the statement `ExplicitCustom();` fails to compile.  The default constructor can still be readded by explicitly defining it alongside other constructors, as shown in the class `ExplicitCustomAndDefault`.

NOTE: Explcitly defining a constructor is **not required** in Zilch as long as every data member of the class has a default constructor.

Destructors are called when all handles to an object are destroyed.  The exception is when an object is not a copy by reference type, in which case the destructor isn't called.

```lang=csharp, name=Destructors
struct MyStruct
{
  var Id : Integer;
  constructor(id : Integer)
  {
    this.Id = id;
  }
  destructor()
  {
    Console.WriteLine(this.Id);
  }
}

class MyClass : MyStruct {}

class Driver2
{
  [Static]
  function MyFunction()
  {
    var v1 = MyStruct(1);
    var v2 = local MyStruct(2);
    var v3 = new MyStruct(3);
    var v4 = MyClass(4);
    var v5 = new MyClass(5);
  } // end of the scope, all unreferenced objects are destroyed
}
```
```name=Console window
3
4
5
```

In the example above, `MyClass` [inherits](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/inheritance.markdown) from `MyStruct`.  `MyClass` has the same members as `MyStruct`, and the only difference between the two is that `MyClass` is a `class`.  Observe how `3`, `4`, and `5` are printed, which means that the destructor got called on `v3`, `v4`, and `v5`.  All struct destructors were ignored, while all class destructors were called.  The one exception is `v3`, which is of the type `ref MyStruct` and has the copy `by-reference` quality.

 # Related Materials
 ## Manual
- [Variables](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/variables_and_data_types.markdown)
- [Functions](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/functions.markdown)
- [memory_management](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/memory_management.markdown)
- [attributes](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/attributes.markdown)
- [inheritance](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/inheritance.markdown)
- [Static](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/attributes.markdown#static)

 ## Code Reference
- [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown) 

 