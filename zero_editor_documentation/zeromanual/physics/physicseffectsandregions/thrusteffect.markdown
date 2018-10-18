The [ThrustEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/ThrustEffect.markdown) component applies a directional force at the center of the attached object. Note that this is different than applying the force through the object's center of mass. If the attached object's center differs from the center of mass then this will apply both a linear and angular force. This effect is often used for thrusters on a ship or other point forces that need to apply torque.

 #  Application Methods
The ThrustEffect component expects to be used as a [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/Colliders.markdown) or Hierarchy effect. These application methods allow the thrust's center to be defined independently of the center of mass of the [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/RigidBody.markdown) If used as a RigidBody effect then this is no different than [ForceEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/ForceEffect.markdown). Other application modes are undefined.

---
 #  Related Materials
 ##  Manual
- [physicseffectsandregions.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions.markdown)
- [ForceEffect.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/ForceEffect.markdown)
- [RigidBody.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/RigidBody.markdown)
- [Colliders.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/Colliders.markdown)

 ##  Reference
- [ThrustEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/ThrustEffect.markdown)
- [PhysicsEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/PhysicsEffect.markdown) 

 