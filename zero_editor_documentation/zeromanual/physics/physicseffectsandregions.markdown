
 #  Overview
[ PhysicsEffects](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/PhysicsEffect.markdown) apply common types of forces to objects. How an effect is applied varies depending on what kind of object it's attached to. Not all attachment modes make logical sense for all effect types. In order, an effect will check for these conditions:
  - [levelsettings](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/architecture/objects/levelsettings.markdown): All objects in the level have this effect applied to them. See [ IgnoreSpaceEffects](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions.markdown#ignorespaceeffects) for exceptions.
  - [ Region ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/region.markdown): All objects in contact with this collision volume (Collider assumed) will have the effect applied to them. Typically, the relevant Collider should be set to Ghost.
  - [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/RigidBody.markdown): If a RigidBody exists without a Region, the effect will apply to the RigidBody's center of mass.
  - [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/Colliders.markdown): If a Collider exists then it is assumed that the effect should apply to the nearest parent RigidBody in the hierarchy. If relevant, the effect will also apply the force at the Collider's position (such as [ThrustEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/ThrustEffect.markdown)).
  - [ PhysicsSpace ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicsspace.markdown): When a physics effect is attached to a space it'll apply to all objects in that space. This option is less preferred to LevelSettings.
  - [ Hierarchy ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/hierarchies.markdown): If an effect does fall into one of the above criteria, it is assumed to apply to the nearest parent RigidBody in the hierarchy.

In the remainder of this page, the wording "global effect" will be used to refer to both LevelSettings and [PhysicsSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/PhysicsSpace.markdown) effect mode types.

 #  PhysicsEffects
The currently available PhysicsEffects are:
  - [GravityEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/ForceEffect.markdown): Applies an acceleration to an object in a direction.
  - [ForceEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/ForceEffect.markdown): Applies a force to an object in a direction.
  - [PointGravityEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/PointForceEffect.markdown): Applies an acceleration towards the center of the effect.
  - [PointForceEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/PointForceEffect.markdown): Applies a force away from the center of the effect.
  - [ThrustEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/ThrustEffect.markdown): Applies a point force on an object based upon the position of the effect.
  - [DragEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/DragEffect.markdown): Applies linear/angular drag/damping to slow down object movement.
  - [FlowEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/FlowEffect.markdown): Applies force to make an object move at a constant speed in a direction. Commonly used to make "tractor beam" like movement.
  - [TorqueEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/TorqueEffect.markdown): Applies a torque (angular force) to an object.
  - [VortexEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/VortexEffect.markdown): Applies a force to make an object circle around a vortex center.
  - [WindEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/WindEffect.markdown): Applies a directional force proportional to the approximate surface area of the object in the wind direction.
  - [BuoyancyEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/BuoyancyEffect.markdown): Applies a buoyancy force to all objects in collision with this shape.
  - [CustomPhysicsEffect ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/CustomPhysicsEffect.markdown): Allows user defined effects via script events.
  
 #  IgnoreSpaceEffects
Occasionally some objects should not have certain global effects applied to them, such as gravity or drag. One solution to this is to remove the relevant effects from LevelSettings/Space and add the effect to every RigidBody instead. This quickly becomes impractical as the number of objects increases. Instead the problem can be approached from the opposite direction: telling certain objects to ignore global effects. The [IgnoreSpaceEffects](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/IgnoreSpaceEffects.markdown) component tells an object to not apply global forces of certain types.

 #  Troubleshooting
Sometimes a PhysicsEffect will not behave as desired. When trying to troubleshoot what is going wrong there are a few key considerations:
  - What application mode is being used? Is this behaving as a Region effect? LevelSettings? etc...
  - What space is the effect being applied in? Most effects have some kind of local space property that determines if the effect takes into account the object's Transform. If unexpected behavior happens when an object rotates then look for a property like this.
  - When trying to apply a Region effect, it's common to forget to make the relevant Collider ghost. In this scenario objects will still get the effect applied when in contact but will additionally undergo collision resolution.
  - If the effect happens once but doesn't happen again, it may have a RigidBody component that is causing it to move (e.g. by gravity).

---
 #  Related Materials
 ##  Manual
- [RigidBody.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/RigidBody.markdown)
- [Colliders.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/Colliders.markdown)
- [PhysicsSpace.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/PhysicsSpace.markdown)
- [levelsettings](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/architecture/objects/levelsettings.markdown)
- [ Hierarchy ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/hierarchies.markdown)

 ##  Reference
- [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/RigidBody.markdown)
- [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/Collider.markdown)
- [PhysicsSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/PhysicsSpace.markdown)
- [Region](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/Region.markdown)
- [IgnoreSpaceEffects](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/IgnoreSpaceEffects.markdown)
- [PhysicsEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/PhysicsEffect.markdown)
- [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/Transform.markdown)
 

 