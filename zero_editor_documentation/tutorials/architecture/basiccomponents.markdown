This lesson covers the basics of [ Components ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/architecture/components/components.markdown) and demonstrates basic usage of the [ Collider ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown), [ RigidBody ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/rigidbody.markdown), [ Sprite ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/graphics/sprites/sprite.markdown), and [ SpriteText ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/graphics/sprites/spritetext.markdown) components.


 #  Learning Objectives


- Component basics
- Common built-in components


 #  Component Overview


Each component will typically have its own set of properties that can be modified to customize that component's behavior. In this tutorial we're going to show you some of the most commonly used components.


 #  Level Setup


- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#newproject)
 - Create a new project using the {nav icon=clone, name=Empty 2D Project} template


 ##  Create a Transform Object


- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ CreateTransform](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#createtransform)



![micreatetransform](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/113.png)


*Creating a Transform object via the `Create Menu`*


Notice that the Trasnform object object can be found in the `Objects Window`:


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46956.png)


*The Transform object listed in the `Objects Window`*


This provides a very basic object that has a defined position, scale and rotation. Let's go ahead and make our object more interesting by adding a [Sprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown) component.


 #  Adding a Component


- In the `Properties Window`
 - Click  the `Add Component` button
 - Type key : `Sprite`
 - Click  on Sprite button to add a [Sprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown) component.



![AddSprite](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46957.gif)


*Adding the [Sprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown) component to the Transform object*


You can also add components to a selected object by using the hotkey `Ctrl + M`.

NOTE:
  Some components may require another component to be present on an object before they can be added: this is called a **dependency**. Many of the components in Zero (Including Sprite, for example) depend on the [Transform](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/transform.markdown) component. If one or more dependencies aren't satisfied, Zero will notify you when you attempt to add that component.
  ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46145.png)


 #  Sprite Component


The [Sprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown) component provides a 2D visual representation of an object. Let's take a look at some of its most commonly used properties:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46960.png)


*The `Properties Window` showing the Sprite component*


| Common Sprite Properties |
|---|
| Visible checkBox | Whether the object can be seen |
| VertexColor  | The base color of the Sprite |
| SpriteSource enum | The image file that this Sprite displays |


 #  Making a Copy of an Object


- [ Select](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Transform object
 - Press key `Ctrl + C` to copy it 
 - Press key `Ctrl + V` to paste a new copy

Notice how there are two objects in the `Objects Window`, but we only see one in the `Level Window`. That's because they are overlapping; we can fix this by moving one of the objects.


 # Altering Component Properties



- In the `Properties Window`
 - Rename Transform object to `RedBall`
 - Under [Transform](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/transform.markdown)
  - Set Translation  to `[0, 5, 0]`
    ![Move](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46961.gif)
 - Under [Sprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown)
  - Set SpriteSource enum to `CircleBordered`
    ![SpriteSourceChange](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46962.gif)
  - Set VertexColor  to `[R:255, G:0, B:0, A:1.00]`
    ![ColorChange](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46963.gif)

NOTE:
  Color is defined by four values; Red, Green, Blue, and Alpha, in that order: RGBA. The first three refer to the amount of each respective color, while Alpha denotes the opacity of the color. Color values in the property grid range from 0 to 255, while alpha ranges from 0.00 (fully transparent) to 1.00 (fully opaque).

| Color References |
|---|
| Red     | `[R:255, G:0  , B:0  , A:1.00]` | ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46257.png) |
| Green   | `[R:0  , G:255, B:0  , A:1.00]` | ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46258.png) |
| Blue    | `[R:0  , G:0  , B:255, A:1.00]` | ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46265.png) |
| Yellow  | `[R:255, G:255, B:0  , A:1.00]` | ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46262.png) |
| Magenta | `[R:255, G:0  , B:255, A:1.00]` | ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46294.png) |
| Cyan    | `[R:0  , G:255, B:255, A:1.00]` | ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46276.png) |
| Orange  | `[R:255, G:128, B:0  , A:1.00]` | ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46266.png) |
| Pink    | `[R:255, G:0  , B:128, A:1.00]` | ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46264.png) |
| Purple  | `[R:128, G:0  , B:255, A:1.00]` | ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46275.png) |
| Teal    | `[R:0  , G:255, B:128, A:1.00]` | ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46293.png) |
| White   | `[R:255, G:255, B:255, A:1.00]` | ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46260.png) |
| Black   | `[R:0  , G:0  , B:0  , A:1.00]` | ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46261.png) |

- [ Select](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : the other Transform object object
- Rename it to `Ground`
- In the `Properties Window`
 - Under [Transform](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/transform.markdown)
  - Set Scale  to `[5, 0, 0]`
 - Under [Sprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown)
  - Set VertexColor  to `[R:0, G:255, B:0, A:1.00]`

Your level should look like this:


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46281.png)



 #  RigidBody Component


The [RigidBody](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/rigidbody.markdown) component gives an object physics properties, like mass and velocity. Let's take a look at it:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46964.png)


*The `Properties Window` showing the RigidBody component*


| Common RigidBody Properties |
|---|
| Velocity  | The current velocity being applied to the object. Changing this property in the editor sets the object's initial velocity |
| AngularVelocity  | Angular velocity is an object's current spin. Changing this property in the editor sets the object's initial spin (only around the Z axis for 2D objects) |
| RotationLocked checkBox | Prevents the physics system from rotating the object. (The object can still be rotated by modifying its Transform's Rotation  property.) Commonly used for player characters |

- [ Select](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : RedBall object
- In the `Properties Window`
 - [ Add Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [ RigidBody](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/rigidbody.markdown)
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Save Project](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#saveproject)
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)

The RedBall object  is now affected by gravity.



![FallingBall](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46284.gif)


*The RedBall object object falling due to gravity*


Notice that it didn't collide with the Ground object object, though. To have the RedBall object  hit the ground, we'll need to add [ colliders](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown) to our objects.

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)


 #  Collider Components


Colliders are used to detect when two objects occupy the same physical space, and, if so desired, prevent that. Zero Engine offers several different types of colliders, including [ BoxCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/boxcollider.markdown), [ SphereCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/spherecollider.markdown), [ CylinderCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/cylindercollider.markdown), and [ CapsuleCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/capsulecollider.markdown); in this section, we'll demonstrate a couple of these.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46965.png)


*The `Properties Window` showing the BoxCollider component*


| Common Collider Properties |
|---|
| Offset  | How far the collider should be offset from the object's position |
| Ghost checkBox | Allows for collision detection without resolution |
| Size  | How big the collider should be, relative to the object's scale (only available on BoxCollider) |
| Radius  | How big the radius of the collider should be, relative to the object's scale (only available on SphereCollider) |

- [ Select](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : RedBall object
- In the `Properties Window`
 - [ Add Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [ SphereCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/spherecollider.markdown)

Let's also add a collider to our Ground object object.

- [ Select](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Ground object
- In the `Properties Window`
 - [ Add Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [ BoxCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/boxcollider.markdown)

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Save Project](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#saveproject)
- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)



![FallingBallHit](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46288.gif)


*The RedBall object object landing on the Ground object object*


Now our RedBall object is colliding with the Ground object as intended.

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)


 #  SpriteText Component


Similar to [Sprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sprite.markdown), the [SpriteText](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/spritetext.markdown)  component allows us to draw 2D text onto the screen. Let's take a look at its properties:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46966.png)


*The `Properties Window` showing the SpriteText component*


| Common SpriteText Properties |
|---|
| Visible checkBox | Whether the text can be seen |
| VertexColor  | The color of the text |
| Font enum | Which Font resource resource to use |
| FontSize  | How big the text should be |
| Text  | The actual text to be displayed |

To finish up, the project let's add a Title object.

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSpriteText](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#createspritetext)
- Rename SpriteText object to `Title`
- In the `Properties Window`
 - Under [Transform](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/transform.markdown)
  - Set Translation  to `[0, 7, 0]`
 - [ Add Component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [ SpriteText](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/spritetext.markdown)
 - Under [SpriteText](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/spritetext.markdown)
  - Set FontSize  to `100`
  - Set Text  to `Hello World!`, or your preferred title

Let's take a look at our final result:

- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)



![FallingBallFinal](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46291.gif)


*The RedBall object falls and lands on the Ground object while the Title object says hello*


- [ Command](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)

 #  Related Materials
 ##  Manual
- [components](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/architecture/components/components.markdown)
- [colliders](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown)
- [rigidbody](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/rigidbody.markdown)
- [sprites](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/graphics/sprites.markdown)
- [spritetext](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/graphics/sprites/spritetext.markdown)
- [editorcommands](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands.markdown)
- [selectobject](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown)
- [addremovecomponent](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown)
- [gameobjectsconcept](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/architecture/cogs/gameobjectsconcept.markdown)

 ##  Code Reference
 ###  Commands
- [ NewProject](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#newproject)
- [ CreateTransform](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#createtransform)
- [ SaveProject](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#saveproject)
- [ PlayGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#playgame)
- [ StopGame](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#stopgame)
- [ CreateSpriteText](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/command_reference.markdown#createspritetext)

 ###  Classes
- [Sprite](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Sprite.markdown)
- [transform](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/transform.markdown)
- [rigidbody](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/rigidbody.markdown)
- [collider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/collider.markdown)
- [boxcollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/boxcollider.markdown)
- [spherecollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/spherecollider.markdown)
- [cylindercollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/cylindercollider.markdown)
- [capsulecollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/capsulecollider.markdown)
- [SpriteText](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/SpriteText.markdown) 
  
  
  
  
  
  
  

 