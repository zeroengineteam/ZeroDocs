Attributes are part of the Zilch grammar allowing additional information to be associated with other Zilch constructs, i.e. they may be applied to classes, fields, get-sets, and functions. While some attributes are inherent to the Zilch programming language, the program embedding Zilch may create and assign their own meaning to new attributes as appropriate for their scripting needs. This means that some attributes exist in Zilch, the standalone language, while others are available in Zilch due to the extensions made by the Zero Engine in which it is embedded. 

 # Using Attributes

In Zilch, attributes can be assigned by annotating the affected construct with a capitalized name of the recognized attribute in square brackets above the definition:

```lang=csharp, name=Assigning an Attribute to a Function
[Virtual] // Here we've added the attribute "Virtual" to the function Speak
function Speak() : String
{
  return "...";
}
```

 # Existing Attributes

The following are usable in the Zero Engine:

| Attribute                               | From  | High Concept                                                |
|-----------------------------------------|-------|-------------------------------------------------------------|
| `[Static]`                              | Zilch | Makes construct static                                      |
| `[Virtual]`                             | Zilch | Marks a construct as a polymorphic base                     |
| `[Override]`                            | Zilch | Marks a construct as overriding a base construct            |
| `[Extension(typeid(OtherType))]`        | Zilch | Appends construct to preexisting `OtherType`                |
| `[Display]`                            | Zero  | Allows construct to appear in Property Grid                 |
| `[Serialize]`                          | Zero  | Allows construct value to be saved by Zero                  |
| `[Property]`                            | Zero  | Combines `[Display]` and `[Serialize]`                    |
| `[Dependency]`                          | Zero  | Enables Zero to enforce explicit dependencies               |
| `[RunInEditor]`                         | Zero  | Allows code to run in the editor                            |
| `[Tool]`                                | Zero  | Can run in editor and accessible in Tools Window            |
| `[Command]`                             | Zero  | Can run in editor and accessible in Search Window           |
| `[ComponentInterface]`                  | Zero  | Defines a class as a generic interface for derived classes  |

(IMPORTANT)**Deprecation Warning**: The `[Editable]` and `[Serialized]` attributes were #deprecated in release [1.1.0](https://dev.zeroengine.io/source/ZeroCore/browse/releases%252F1.1.0/;d3c079aaf84bf52abb6e1c43e8ca88361cd70b10) and will be removed in the next major version of the engine. Use `[Property]` and `[Serialize]` for all engine versions `1.1.0` and newer.

 ## [Static]
        
Static can be used on function, fields, and get-sets. These allow you to access fields, get-sets, and functions without first creating an instance of the class in your code. 

```lang=csharp, name=Defining a Static Variable and Function
  class Mathematics
  {
      [Static]
      var PI: Real{ get{return 3.14159292;}}
      [Static]
      function Circumference(radius : Real) : Real
      {
          return Mathematics.PI * radius * radius;
      }
  }
```
Given the class above you can use its functionality by calling into the class's namespace:

```lang=csharp, name=Using Static Variable and Function
  var myNewFavoriteNumber = Mathematics.PI + Mathematics.Circumference(2.0);
  Console.WriteLine(My new favorite number is: `myNewFavoriteNumber`");
```
will result in 

```name=ConsoleWindow
My new favorite number is: 15.708
```

NOTE: While these attributes enable polymorphism, they are still in their infancy. Virtual is to be used with the base class field/get-set/function, while Override is for all the derived classes seeking to write over the base class's field/get-set/function. That said, mixing up `[Virtual]` and `[Override]` , or forgetting the use of the `[Override]` may still provide desired results. To promote forward compatibility, we highly encourage the correct, indicated usage.

 ## [Virtual]

Virtual is used to give Base classes the ability to determine some functions as being able to be overridden by its derived classes.

```lang=csharp, name=Applying Virtual to a Function
class Animal
{
  [Virtual]
  function Speak() : String
  {
    return "...";
  }
}
```

 ## [Override]
Override is used by a derived class to mark the intentional overriding of a base class's virtual function.

```lang=csharp, name=Applying Override to a Function
class Dog : Animal
{
  [Override]
  function Speak() : String
  {
    return "Woof";
  }
}
```

 ## [Extension(typeid(OtherType))]

This allow you to add functionality to a preexisting class from inside another. Currently, you can only extend a class by adding get-sets and functions (i.e. you cannot add fields). If a function is being added to an existing class (`Math`, for example), the [Static] attribute should also be used:

```lang=csharp, name=Applying Extension Attribute to a Function
class MyClass : ZilchComponent
{
  [Extension(typeid(Math))][Static]
  function Circumference(radius : Real) : Real
  {
    return Mathematics.PI * radius * radius;
  }
}
```

Zero works with Zilch to offer these additional attributes:

 ## [Display]

Allows you to set a field or get-set via the Property Grid in the editor. Because this doesn't save the settings, it is usually used in conjunction with either `[RunInEditor]` or `[Serialize]` . For example, changing

```lang=csharp, name=Variable without Display Attribute
class MyClass : ZilchComponent
{
  var MyVariable : Real;
}
```
to

```lang=csharp, name=Variable with Display Attribute
[Editiable]
var MyVariable : Real;
```

results in the the variable appearing in the Property Grid in Properties window:



![Editable](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/66612.png)


 ## [Serialize]

Allows a value to be saved by the Engine. This allows a field and get-sets to be saved with ObjectStore. When used with `[Display]` it allows the values to be saved from the Property Grid so that they may be loaded in an instance of the game. 

 ## [Property]

Property wraps the `[Display]` and `[Serialize]` attributes together into one. As implied by the use of `[Display]` and `[Serialize]`, it works on fields and get-sets. Properties of certain types will result in unique set fields in the Property Grid. For example,

```lang=csharp, name=Variables with Property Attribute
class MyClass
{
  [Property]
  var MyColor : Real4;

  [Property]
  var  MyMaterial : Material;
}
```
results in



![Property](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/66615.png)


 ## [Dependency]

Allows the programmer to make a dependency between components explicit. This allows users to determine the interrelatedness without having intimate knowledge of a component's inner workings. The Zero Engine supports this by requiring dependencies to be added prior to attaching the component, preventing the removal of dependencies while the component is still attached, and safeguarding the order of initialization of components such that the dependencies will always be initialized first. 

The below sample demonstrates the declaration of a dependence upon another component:

```lang=csharp, name=Applying the Dependence Attribute on Another Component
  class SimpleOffset : ZilchComponent
  {
      // Declaring that SimpleOffset depends upon Transform component.
      [Dependency]
      var Transform : Transform = null; 
      function Initialize(init : CogInitializer)
      {
          // This declaration also physically adds that variable to our fields: 
          // Since this.Transform contains the component we have a dependency 
          // on, we can access it without going through the Owner. 
          this.Transform.Translation += Real3(0,5,0);
      }
  }
```

The `[Dependency]` attribute may also be used on get-sets.

NOTE: **Did you know?** When working in the editor, the space the objects operate in is paused. This means that the `LogicUpdate` event will never fire, and that Actions on objects never get updated! In order to receive continuous events, the object should connect to `UpdateFrame` instead.


 ## [RunInEditor]

When placed on a class derived from ZilchComponent, it changes proxy objects into live objects upon being attached in the editor. This means that the object will run its code in the editor. When *any* scripting file is saved in the editor, all live objects (i.e. those with the RunInEditor component attached) will, by default, have their object destroyed, recreated, and its data reinitialized. 

IMPORTANT: Any code you choose to run via `[RunInEditor]` can result in editor instability. For instance, if you choose to loop through and destroy all the objects and save your game you may lose your ability to recover the lost objects, and have to recreate them by hand. Undo and Redo operations for RunInEditor components must be handled by the programmer!  

 ## [Tool]

Allows for a tool to be hooked into the Tools Window such that it shows up in the drop down menu, and can be used in the editor. When creating a new custom tool, a good starting point is generating the ZilchScript with the Tool template chosen in the Add Window.

 ## [Command]

Allows for a class to be hooked into the command system such that it shows up, and can be ran, from Zero's Search Window. The following Paste provides a template for a custom Command that creates an object based on an archetype, allowing the user to make their own "Create" commands similar to `CreateCube` and `CreateSphere`:

```
[Command(autoRegister:true)]
class CreateArchetype : ZilchComponent
{
  // The archetype from which to create an object
  var ArchetypeToCreate : Archetype = Archetype.MyObject;
  
  // The position at which to create the object
  var Position : Real3 = Real3(0, 1, 0);
  
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Owner, Events.CommandExecute, this.OnCommandExecute);
  }

  function OnCommandExecute(event : CommandEvent)
  {
    var selection = Zero.Editor.Selection;
    selection.SelectOnly(this);
    selection.FinalSelectionChanged();
    
    this.CreateObject();
  }
  
  function CreateObject()
  {
    // Create the object in Editor space
    var editorSpace = Zero.Editor.EditSpace;
    editorSpace.CreateAtPosition(this.ArchetypeToCreate, this.Position);
  }
}

```


 ## [ComponentInterface]
The ComponentInterface attribute allows the user to define a class as a generic interface for its derived types. One common example of this is [collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collider.markdown), which acts as a component interface for all collider types, such as [boxcollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/boxcollider.markdown), [capsulecollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/capsulecollider.markdown), and more. Defining an interface using this attribute allows the user to access the members of a derived class using the component name of the base class.

```name=Component Interface Access Example, lang=csharp
var collisionGroup = this.Owner.BoxCollider.CollisionGroup;
var collisionGroupAccessedByInterface = this.Owner.Collider.CollisionGroup;

if(collisionGroup == collisionGroupAccessedByInterface)
  Console.WriteLine("These variables reference the same component");
```

Using a component interface does not mean that the property and methods of a derived class need to be exactly the same as the base class. What would be the point? Using the [ Virtual](https://github.com/zeroengineteam/ZeroDocs/blob/master/sandbox/arend_danielek/attributes.markdown#virtual) and [ Override ](https://github.com/zeroengineteam/ZeroDocs/blob/master/sandbox/arend_danielek/attributes.markdown#override) attributes, we can modify the interface of derived classes.

```name=Component Interface Example, lang=csharp
[ComponentInterface]
class AnimationDebugNode : ZilchComponent
{
  [Virtual]
  var Node : AnimationNode;
  
  function Initialize(init : CogInitializer)
  {
    
  }
}

class SelectiveDebugNode : AnimationDebugNode
{
  [Override]
  var Node : SelectiveNode;
}

class DirectBlendDebugNode : AnimationDebugNode
{
  [Override]
  var Node : DirectBlend;
}

class CrossBlendDebugNode : AnimationDebugNode
{
  [Override]
  var Node : CrossBlend;
}
```

 # Parameters in Attributes

Attributes can also take parameters; below is the template generated for creating a new Command by Zero:

```lang=csharp
[Command(autoRegister:true)] // This template file sets a parameter, autoRegister, to true.
class MyNewCommand : ZilchComponent
{
  function Initialize(init : CogInitializer)
  {
      Zero.Connect(this.Owner, Events.CommandExecute, this.OnCommandExecute);
  }

  function OnCommandExecute(event : CommandEvent)
  {
    Console.WriteLine("MyNewCommand Command Executed");
  }
}
```
At this time, only Extension, Tool, and Command attributes take parameters. 

 - Extension requires the type you are using to extend the attribute, as a parameter. 

 - Tool and Command have the optional parameter to automatically register the component with the engine. 

To manually register, you would add these components to an archetype and then add the Tool or Command editor tag via the Library Window, respectively. Registering manually gives you access to the archetype, making it possible to leverage component-based design in the construction of new Tools and Commands.

 # Related Materials
 ## Manual
- [inheritance](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/inheritance.markdown)
- [variables_and_data_types](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/variables_and_data_types.markdown)
- [wysiwyg](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/scripting/wysiwyg.markdown) 

 