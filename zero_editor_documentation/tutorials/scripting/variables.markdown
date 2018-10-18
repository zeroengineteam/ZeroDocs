This lesson covers the basics of using Variables in [Zilch](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero.markdown).

 # Learning Objectives

- Learn how to declare variables
- Understand the common variable types
- Learn how to access external variables

 # Level Setup

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#newproject)
 - Create a new project using the {nav icon=clone, name=Empty 2D Project} template
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite)
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `MyBehavior`
- In the `Level Window`
 - [Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Sprite object
- In the `Properties Window`
 - Rename Sprite object to `Square`
 - [Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent/) : `MyBehavior`

 # Class Variables

A variable is a stored value of a given type. In order to manipulate a variable you must know its type and what values it can hold. Below is a table of the most common variable types in [Zilch](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero.markdown).

| Type| Acceptable Values | Common Operators|
|---|---|---|
| [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown) | `true` `false`| `=` |
| [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown) | `1` `-2` `100` etc| `=` `+` `-` `*` `/` `+=` `-=` `*=` `/=` `++` `--` |
| [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown) | `0.1` `-1.2` `3.1415926`, etc | `=` `+` `-` `*` `/` `+=` `-=` `*=` `/=` `++` `--` |
| [real2](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real2.markdown) | `Real2(0.1, -2.5)` etc |  `=` `+` `-` `*` `/` `+=` `-=` `*=` `/=` |
| [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown) | `Real3(0.1, -2.5, 19.0)` etc |  `=` `+` `-` `*` `/` `+=` `-=` `*=` `/=` |
| [real4](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real4.markdown) | `Real4(0.1, -2.5, 19.0, 0.0)` etc |  `=` `+` `-` `*` `/` `+=` `-=` `*=` `/=` |
| [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown) | `Hello World!` etc | `=` |

Variables are used to represent values your game needs to perform its logic such as, Lives, Ammo, Run Speed and more. Let's create a new variable for our `MyBehavior` component class.

We can declare (create) a variable by typing the following code within the class scope:

```lang=csharp, name=Class Variable Declaration
var Speed : Real = 0.1;
```

`var` - Indicates that we want to create a new variable
`Speed` - The name of our variable. A class variable's name must be capitalized.
`: Real` - Denotes that the variable we are creating is of type Real.
`= 0.1` - The assigned starting value for our variable (0.01 in this case). 
`;` - Indicates that we're done with instructions on this line of code.

Here is what your code should look like:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/66925.png)


 # Operators

Operators are special symbols used to manipulate or compare variables. Let's look at the different ways of modifying our `Speed` variable.

 ## Assignment `=`

The assignment operator sets the value of the variable on its left (known as the left-hand operand) to the value on its right (the right-hand operand). The left-hand operand must be a variable, while the right-hand operand may be a literal value, another variable of the same type, or an expression that combines both.

Examples:

```lang=csharp, name=Literal Assignment
this.Speed = 5.0;
```

```lang=csharp, name=Variable Assignment
var Pi : Real = 3.1415926;

this.Speed = this.Pi;
```

```lang=csharp, name=Expression Assignment
var Pi : Real = 3.1415926;

this.Speed = this.Pi + 5.0;
```

NOTE: Class variables are accessed by using the `this` keyword; which refers to the class object we're currently in, that is the `MyBehavior` component. We then use the dot `.` operator to indicate that we want a member of the object on the left of it. Thus by typing `this.Speed` we're indicating "The variable named `Speed` that is a member of the class we're currently in".

 ## Arithmetic Operators `+` `-` `*` `/`

Applicable to arithmetic types (Integer, Real, Real2, Real3, etc) these allow you to create expressions the perform the corresponding math operations:

 - `+` - Add
 - `-` - Subtract
 - `*` - Multiply
 - `/` - Divide

```lang=csharp, name=Addition Increment
this.Speed = this.Speed + 1.0;
```

```lang=csharp, name=Multiplication of the Current Value
this.Speed = this.Speed * 2.0;
```

NOTE: If the value of the arithmetic operation isn't stored in a variable, then the operation has no repercussion and will be ignored.

 ## Arithmetic Assignment Operators `+=` `-=` `*=` `/=`

These operators let you add, subtract, multiply and subtract the values on the right of the operator to the current value of the variable on the left of it. They are only available for arithmetic types.

Example:

```lang=csharp, name=Arithmetic Assignment
var Speed : Real = 1.0;

this.Speed += 2.3;

//The value of this.Speed is now 3.3
```

NOTE: Using these operators is logically equivalent to preforming the corresponding operation using the variable itself on the right of the assignment operator. For example, `this.Speed += 5.0;` is the same as `this.Speed = this.Speed + 5.0;`.

 ## Increment and Decrement Operators `++` `--`

These are used in combination with Integer and Real types to either add or subtract `1` to the current value of the variable. In [Zilch](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero.markdown), these are always used before the variable you want to increment.

Example:

```lang=csharp, name=Increment Operator
++this.Speed;
```

NOTE: Using `++this.Speed;` is logically equivalent to `this.Speed += 1.0;` and only exists for convenience.

 # Accessing Properties

Up until now we have modified properties on various components through the `Properties Window`, but internally, those properties are just variables we can manipulate in code at runtime (while the game is running).

Let's try and modify our Square object to move to the right based on our speed. So the value we're looking to modify is the Translation  property in the [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown) component and we want to do that on Logic Update so that it happens every frame.

 - Add the following line of code inside LogicUpdate:

```lang=csharp, name=Accessing Properties
this.Owner.Transform.Translation += Real3(this.Speed, 0, 0);
```
|`this.` | Refers to the class we're currently in (In this case the MyBehavior component) |
|`Owner.` | The object that owns this component. |
|`Transform.` | The component we're trying to access. |
|`Translation` | The property (or variable) we want to modify. |

NOTE: `this.Owner.Transform.Translation` can be interpreted as "The Translation  property of the [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown) of the object that owns this component"

|`+=` | Add and assign operator to add a value to the current translation. |
|`Real3(X, Y, Z)` | Here we create a Real3 since that's the type of the Translation  property we're looking to modify. Real3s are composed of three Real values which are referred to X, Y and Z in order. |
|`this.Speed, 0, 0` | Here we're accessing the `Speed` variable created earlier and using it as the X value. We'll just use 0 for Y and Z. |
|`;` | Indicates that we're done with instructions on this line of code.|

Here's what your code should look like:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/66927.png)


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)



![Game2](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/66929.gif)


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

 # Dependencies

Previously, we demonstrated how to access a property of another component. However, we have made the assumption that our owner object had that component; if it didn't Zero would give us an error:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/66931.png) 


To prevent this, we can declare a dependency on the [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown) component. 

 - Add the following line at the beginning of the class scope:

```lang=csharp, name=Dependencies
[Dependency]  
var Transform : Transform;
```

By adding this we prevent the addition of the `MyBehavior` component to objects without a [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown) component. The `[Dependency]` part is an **attribute** that modifies the following variable; you can find more information about them in the [Attribute Manual Page](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/attributes.markdown).



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/66933.png)


NOTE: This also allows us to shorten part our previous line of code `this.Owner.Transform.Translation` to just `this.Transform.Translation` since we're already referencing the dependency.

Once the dependency is declared, dependent components can't be removed unless no dependent components are removed first.

- Attempt to remove the [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown) component from Square object.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/89070.png)



 ## Properties

It is also possible to turn your class variables into properties that can be accessed and modified via the `Properties Window`. To accomplish that we add the `[Property]` attribute before the variable declaration.

 - Add the `[Property]` attribute to the `Speed` variable:

Here's what it should look like:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/89072.png)


We can then find the `Speed` property and edit it in the `Properties Window`.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/66983.png)


- [Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Sprite object
- In the `Properties Window`
 - Under `MyBehavior`
  - Set Speed  to 0.02
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)

Notice that the object moves a lot slower now, in accordance with the `0.02` value we set on the `Properties Window` and **NOT** the initial value of `0.1` given when the function was declared. Once a variable is given a Property attribute; its values are *serialized* and will match the one listed in the `Properties Window`.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

 # Local Variables

Local Variables are defined within the scope of a function or nested scope are called local variables; they must begin with lower case letter and will cease to exist at the end of the scope in which they were created in. Local variables are useful when calculating value that do not need to persist outside a scope.

Example:

```lang=csharp, name=Local Variable Declaration
var lives : Integer = 3;
```

 # Putting it all Together

Now that we've seen the basics of using variables, let's move create a variable to determine the direction the Square object object should move.

- In the `MyBehavior` script
 - Add the following  property:

```lang=csharp, name=Direction Property
[Property]
var Direction : Real2 = Real2(1.0, 1.0);
```
- In the `MyBehavior` script
 - Replace the previous content of the LogicUpdate function with the following:

```lang=csharp, name=New LogicUpdate
function OnLogicUpdate(event : UpdateEvent)
{
  var normalized_direction : Real2 = Math.Normalize(this.Direction);
  this.Owner.Transform.Translation += Real3(normalized_direction * this.Speed, 0.0);
}
```

Here we create a local variable that is the normalized value given by the Direction property; that is, a vector that points in the same direction but of length `1.0`. We then used that normalized direction to construct a Real3 (out of a Real2 and a Real), multiplying the direction by our `Speed` property and assign it to the Square object's translation.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)



![SquareMoveInDirection](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/89074.gif)


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

 # Related Materials

 ## Manual
- [Components](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/architecture/components.markdown)
- [ Zilch User Documentation](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero.markdown)
- [ Variables](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/variables_and_data_types.markdown)
- [Attributes](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/attributes.markdown)
- [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)

 ## Reference
 ### Classes
- [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
- [Sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/sprite.markdown)
- [ZilchScript](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/zilchscript.markdown)

 ### Zilch Base Types
- [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)
- [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)
- [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)
- [real2](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real2.markdown)
- [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)
- [real4](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real4.markdown)
- [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 ### Commands
- [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite)

 ## Tutorials
- [CustomComponents](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/scripting/customcomponents.markdown)
 

 