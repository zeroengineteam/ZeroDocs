This lesson covers how to handle basic keyboard input in Zero Engine.


 # Learning Objectives

- Checking for keyboard input

 # Level Setup
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#newproject)
 - Create a new project using the {nav icon=clone, name=Empty 2D Project} template
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/createobject.markdown)
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `CharacterLogic`
- [Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Sprite object
- In the `Properties Window`
 - Rename Sprite object to `Character`
 - [Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `CharacterLogic`

 # Keyboard Input

A critical part of making a game is to allow the user to interact with it. The simplest way to achieve that is to query the available hardware for input and have the simulation respond to it.

 - Update the `CharacterLogic` script to the following code block:

```lang=csharp, name=Keyboard Input
class CharacterLogic : ZilchComponent
{
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }

  function OnLogicUpdate(event : UpdateEvent)
  {
    if(Zero.Keyboard.KeyIsPressed(Keys.Space))
    {
      this.Owner.Sprite.VertexColor = Colors.Red;
    }
  }
}
```
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)
 - Press key `Space`



![SimpleInput](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/89953.gif)


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

Let's take a closer look inside our if statement:

| Zero.Keyboard.KeyIsPressed(Keys.Space); |
|-----------------------------------------------|
| [Zero](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/zero.markdown) | Accessing the Zero engine class |
| [Keyboard](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/keyboard.markdown) | Accessing Keyboard class |
| [KeyIsPressed](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/keyboard.markdown#keyispressed-zero-engine)(...); | Function that determines whether a given key has been pressed this frame |
| [Keys](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#keys) | Enumeration containing all keyboard keys |
| .Space |  The enumeration index corresponding to the `Space` key |

Here are all Keyboard functions:

| Keyboard Functions |
|-----------------------|
| [KeyIsDown](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/keyboard.markdown#keyisdown-zero-engine-do) | Checks whether a given key is currently down this frame |
| [KeyIsUp](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/keyboard.markdown#keyisup-zero-engine-docu) | Checks whether a given key is currently down this frame|
| [KeyIsPressed](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/keyboard.markdown#keyispressed-zero-engine) | Checks whether a given key was pressed this frame |
| [KeyIsReleased](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/keyboard.markdown#keyisreleased-zero-engin) | Checks whether a given key was released this frame |

(NOTE) **Enumerations** - 
An enumeration (or enum) is a data type that groups items assigning each a unique name under the enumerated list. Items can be referenced by accessing the type followed by a `.` and the name of the desired item (i.e. [Keys.Space](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#keys) or Colors.Red). You can read more on enumerations [ here ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/enums.markdown).

 # Dynamic Character Controller

Let's use what we just learned to create a character controller for a simple platformer.

 ## Character Setup

- [Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Character object
- In the `Properties Window`
 - [Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown)
 - [Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [BoxCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/boxcollider.markdown)
 - Under [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown)
  - Set RotationLocked checkBox to `true`

 ## Ground Setup

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/createobject.markdown)
- [Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Sprite object
- In the `Properties Window`
 - Rename Sprite object to `Ground`
 - [Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [BoxCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/boxcollider.markdown)
 - Under [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
  - Set Translation  to `0.0, -3.0, 0.0`
  - Set Scale  to `8.0, 0.0, 0.0`
 - Under [Sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/sprite.markdown) 
  - Set SpriteSource texture to `Square`
  - Set VertexColor  to Green `[R:0, G:255, B:0, A:1.00]`

 ## Movement Code

 - In the `CharacterLogic` script
  - Replace the previous `LogicUpdate` function with the following:

```lang=csharp, name=Movement Logic
function OnLogicUpdate(event : UpdateEvent)
{
  var speed : Real = 5.0;
  var xDir : Real = 0.0;
  
  if(Zero.Keyboard.KeyIsDown(Keys.Right))
  {
    xDir += 1.0;
  }
  
  if(Zero.Keyboard.KeyIsDown(Keys.Left))
  {
    xDir += -1.0;
  }
  
  this.Owner.RigidBody.Velocity = Real3(xDir * speed, this.Owner.RigidBody.Velocity.Y, 0.0);
}
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)
 - Press key `Left` and `Right`



![CharacterMovement](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/89976.gif)


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

 # Related Materials

 ## Manual
- [Sprites](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/sprites.markdown)
- [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/rigidbody.markdown)
- [Colliders](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown)
- [KeyboardInput](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/gameplay/input/keyboardinput.markdown)
- [ Enumerations ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/enums.markdown)
- [Create a New 2D Project](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/ZeroManual/Editor/EditorCommands/LauncherNewProject.markdown)
- [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/createobject.markdown)
- [Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)

 ## Reference
 ### Classes
- [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
- [Sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/Sprite.markdown)
- [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown)
- [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collider.markdown)
- [BoxCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/boxcollider.markdown)
- [keyboard](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/keyboard.markdown)
- [Zero](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/zero.markdown)

 ### Enums
- [Keys](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#keys)

 ### Commands

- [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)
- [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame) 

 