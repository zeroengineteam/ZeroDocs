This lesson covers the basic ways to rotate an object in 2D at runtime.


 #  Learning Objectives


- Rotation basics
- EulerAngles
- The ToRadians function
- Simple 2D vector math


 #  Level Setup


- [Create a New 2D Project](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/ZeroManual/Editor/EditorCommands/LauncherNewProject.markdown)
- [Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : GameCamera object
- In the `Properties Window`
 - Under [Camera](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/camera.markdown)
  - Set Size  to `5`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `Rotate2D`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite)
- In the `Properties Window`
 - Rename Sprite object to `Parent`
 - Under [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
  - Set Translation  to `[0, 0, 0]`
 - [Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `Rotate2D`
 - Under [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
  - Hover the cursor over the name of the [Transform.Rotation](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown#rotation-zero-engine-doc) property.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94052.png)


*Hovering over [Transform.Rotation](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown#rotation-zero-engine-doc)*


As you can see, rotational data is saved as a [Quaternion](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/quaternion.markdown). As a high-level developer, you do not need to know how Quaternions work, but you will need to know how to use them. In the `Properties Window`, Quaternions are represented by three angles that are the rotation of the object around the corresponding three axes; these are called Euler (pronounced “oil-er”) angles. In this lesson, we will be working with a 2D game, so we only need to worry about the Z-axis rotation.

Rotation  can be changed either through the `Properties Window` or via accessing the [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown) component in script.

 # Simple Rotating on Update

- In `Rotate2D`
 - Replace the script's content with the following code block

```name=Rotate2D, lang=csharp
class Rotate2D : ZilchComponent
{
  [Dependency] var Transform : Transform;
  
  //45 degrees per second
  [Property]
  var Speed : Real = 45.0;
  
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }

  function OnLogicUpdate(event : UpdateEvent)
  {
  }
}
```

This first type of rotation to look at is //continuous rotation//, which is common in 2D games. It's often very simple, since, depending on the perspective of the game (top down or side view), an object may only ever need to rotate around a single axis.

The first thing we need in order to rotate an object is a speed, which we have defined as a member variable of Rotate2D. The next item needed for this example is our update loop. Just as with translating an object, we want the rotation to appear smoothly interpolated over time, so we will need to rotate just a little bit each frame.

- In `Rotate2D`
 - Update the `OnLogicUpdate` function to the following
```name=Continuous Rotation On Update, lang=csharp
function OnLogicUpdate(event : UpdateEvent)
{
  //convert rotation speed to radians
  var speedRadians = Math.ToRadians(this.Speed);
  //define which axis to apply the rotation on
  var eulerAngles = Real3(0,0,speedRadians);
  //scale the rate of rotation to the framerate
  var frameEulerAngles = eulerAngles * event.Dt;
  //convert the rotation to quaternion so we can pass it to the Transform's rotation functions
  var frameRotation = Math.ToQuaternion(frameEulerAngles);
  //rotate the object
  this.Transform.RotateWorld(frameRotation);
}
```
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)



![RotateOnUpdate](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94054.gif)


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

 # Local vs World Rotation
You may have noticed the name of the function [RotateAnglesWorld](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown#rotateanglesworld-void), and wondered why there is also a [RotateAnglesLocal](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown#rotateangleslocal-void) function. Let's take a closer look at these functions.

 ## Parent RotateWorld
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite)
- [Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Sprite object
- In the `Properties Window`
 - Rename Sprite object to `Child`
 - Under [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
  - Set Translation  to `[0, 1, 0]`
 - Under [Sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/sprite.markdown)
  - Set VertexColor  to `[R:255, G:0, B:0, A:1.0]`
- [Attach](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/architecture/hierarchies.markdown) Child object to Parent object

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)



![RotateWorldParent](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94069.gif)


Now we can see that a child object rotates with its parent. You may have seen similar behavior when using the rotation tool with hierarchies in the past. It is important to note that the Child object maintains it's translation relative to the parent object as the parent object rotates.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

 ## Child RotateWorld
- [Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Child object
- In the `Properties Window`
 - [Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `Rotate2D`
- [Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Parent object
- In the `Properties Window`
 - [Remove Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `Rotate2D`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)



![RotateWorldChild](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94071.gif)


Here we can see that rotating the Child object has no affect on the Parent object.

(NOTE)[Transform.RotateWorld](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown#rotateworld-void) vs [Transform.RotateLocal](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown#rotatelocal-void): You may have noticed the RotateLocal function on Transform. `Local` and `World` refer to to the axes that the rotation will be applied to. RotateWorld rotates an object around its world axes, while RotateLocal rotates it around the axes of its parent object (if any). This is done by applying the rotation of the parent object to the child after the child applies its own rotation.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

 # Rotating with Actions
Rotating on update is useful when trying to rotate in a specific direction, continuously, or more than 360 degrees. However, we often want an object to make quick small rotations to a specific target rotation. This is where rotating with [Actions](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/scripting/actions.markdown) is very convenient.

- In `Rotate2D`
 - Update the `Rotate2D` class to look like the following code block

```name=Rotate With Actions, lang=csharp
class Rotate2D : ZilchComponent
{
  [Dependency] var Transform : Transform;
  
  [Property]
  var TargetRotation : Real3 = Real3(0,0,45);
  
  [Property]
  var Duration : Real = 1.0;

  function Initialize(init : CogInitializer)
  {
    var targRot = Math.ToQuaternion(Math.ToRadians(this.TargetRotation));
    var rotAction = Action.Property(this.Owner.Actions,
                                    @this.Transform.Rotation,
                                    targRot,
                                    this.Duration,
                                    Ease.Linear);
  }
}
```

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)



![ActionRotate](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94073.gif)


*Rotating the child object to 45 degrees on the Z-axis using an Action*


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

- [Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Child object
- In the `Properties Window`
 - Under `Rotate2D`
  - Set `TargetRotation` to `[0,0,405]`

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)



![ActionRotate](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94073.gif)


*Rotating the child object to 405 degrees on the Z-axis using an Action*


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

Notice how both rotations appear the same. Now one may expect the object to make a full 405 degree rotation. However, in the constructor of [Quaternion](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/quaternion.markdown) the angle is normalized to the range of `[0, 360]` degrees. Since 405 degrees is equivalent to 45 degrees, that is the rotation of the [Quaternion](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/quaternion.markdown) that is passed to the action constructor.


 # Related Materials
 ## Manual
- [Create a New 2D Project](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/ZeroManual/Editor/EditorCommands/LauncherNewProject.markdown)
- [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
- {icon university}[[zero_engine_documentation/zero_editor_documentation/zeromanual/editor/addremovecomponent/|Add/Remove Component]]

 ## Tutorials
- [Actions](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/scripting/actions.markdown) 
- [Attach](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/architecture/hierarchies.markdown)

 ## Reference
 ### Classes
- [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
- [Sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/sprite.markdown)
- [Quaternion](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/quaternion.markdown)
- [Camera](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/camera.markdown)

 ### Commands
- [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)
- [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)
- [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite)
 ## Tasks
- T1174 

 