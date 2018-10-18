This lesson focuses on teaching the basics of physics effects and components.

 # Learning Objectives

- [GravityEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gravityeffect.markdown) and [DragEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/drageffect.markdown) components
- Apply / Ignore physics effects on objects
- Basic uses of `name=LevelSettings, icon=cog`

 # Level Setup
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#newproject)
 - Create a new project using the {nav icon=clone, name=Empty 2D Project} template
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite)
 - [Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown)
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)



![FallingSquare](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46396.gif)


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

 # GravityEffect

When running the game, we can see the square object falling. As we mentioned in previous tutorials, the [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown) component allows an object to be subjected by physics forces. However, it is **not** the one responsible for the object falling.

Let's take a look at the LevelSettings object in our level:

- In the `Objects window`
 - [Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : LevelSettings object



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46967.png)


- In the `Properties window`
 - Under [GravityEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gravityeffect.markdown)



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46968.png)


| Common GravityEffect Properties |
|------------|
| Active checkBox    | Whether this component applies force or not |
| Strength    | The magnitude of the force applied |
| Direction   | The direction which force is applied (normalized) |
|LocalSpaceDirection checkBox | Whether the specified direction is local (true) or global (false) |

- In the `Properties window`
 - Under [GravityEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gravityeffect.markdown)
  - Set Active checkBox to `false`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46414.png)


Notice that the Sprite object isn't being affected by gravity anymore. That's because components that produce physics effects, when attached to the LevelSettings object object, will apply that effect to all objects within the Space.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

Let's try and move the Sprite object in other ways:

- [Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Sprite object object
- In the `Properties Window`
 - Under [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown)
  - Set Velocity  to `[3.0, 0.0, 0.0]`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)



![SlowingSquare](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46429.gif)


The Sprite object appears to be moving in the desired direction and still isn't affected by gravity but it slowed down and stopped. But according to Newton's first law of motion; an object retains its movement at a constant velocity unless acted upon by an external force. So what external force caused our object to stop?

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

 # DragEffect 

Let's take a look again at the LevelSettings object:

- [Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : LevelSettings object
- In the `Properties Window`
 - Under [DragEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/drageffect.markdown)
   ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46969.png)
   - Set Active checkBox to `false`

| Common DragEffect Properties |
|------------|
| Active checkBox  | Whether this component applies force or not |
| LinearDamping    | The amount of damping applied to the object's velocity |
| AngularDamping    | The amount of damping applied to the object's angular velocity |

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)



![EverMovingSquare](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46484.gif)


The [DragEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/drageffect.markdown)  exists to simulate air resistance and other forces that would prevent your object from moving indefinitely.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

 # Adding Physics Effects to Objects

These effects can also be applied to individual objects, let's take a look:

- [Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Sprite object
 - [Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [GravityEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gravityeffect.markdown)
 - [Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [DragEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/drageffect.markdown)
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)




![FallingSquare](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46396.gif)


Now we get the same result we had initially, but we could tweak individual gravity and drag effects per object.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

WARNING: GravityEffect (and some other PhysicsEffects) have the LocalSpaceDirection checkBox property set to true by default. This means that, as the object rotates, the "down direction" will be constantly changing. Set LocalSpaceDirection checkBox to false to avoid this behavior.


![TumblingSquare](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46531.gif)


 # IgnoreSpaceEffects

Lastly, let's say you wanted all objects in your level to be affected by gravity except for a few. You could turn off the [GravityEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gravityeffect.markdown) on LevelSettings object and add a [GravityEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gravityeffect.markdown) component to every object that needs it but that would be a lot of work.

Alternatively, you could leave the [GravityEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gravityeffect.markdown) on LevelSettings object on and just add the [IgnoreSpaceEffects](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/ignorespaceeffects.markdown) component to the objects that you don't want gravity on:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46970.png)


NOTE: The [IgnoreSpaceEffects](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/ignorespaceeffects.markdown) component will only stop physics effects attached to LevelSettings object or Space to affect the object; if the object has a [GravityEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gravityeffect.markdown) component or any other physics effects components on itself, they will not be ignored!

 #  Region

The region component can be used to apply any physics effects (Gravity, Drag, etc) to  a specific zone. It works by using a Collider (which it has a dependency on) as a trigger volume to determine whether objects are inside it and then applies the specified force effects.

- [Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite)
- In the `Property Window`
 - Rename Sprite object to `RegionEffect`
 - Under [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)  
  - Set Scale  to `[5, 5, 5]`
 - [Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [BoxCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/boxcollider.markdown)
 - Under [BoxCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/boxcollider.markdown)
  - Set Ghost checkBox to `true`
 - [Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [Region](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/region.markdown)


NOTE: Experiment by adding the [ForceEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/forceeffect.markdown) , [BuoyancyEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/buoyancyeffect.markdown) and [WindEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/windeffect.markdown)

 # Related Materials

 ## Manual
- [Physics Effects & Regions](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions.markdown)
- [ Colliders ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown)
- [ RigidBody ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/rigidbody.markdown)

 ## Code Reference
 ### Classes
- [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
- [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown)
- [BoxCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/boxcollider.markdown)
- [Region](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/region.markdown)
- [GravityEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gravityeffect.markdown)
- [DragEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/drageffect.markdown)
- [ForceEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/forceeffect.markdown)
- [BuoyancyEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/buoyancyeffect.markdown)
- [WindEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/windeffect.markdown)

 ### Commands
- [Create a New 2D Project](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/launchernewproject.markdown)
- [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
- [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)
- [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)
- [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite) 

 