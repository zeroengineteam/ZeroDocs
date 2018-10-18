The [DragEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/DragEffect.markdown) component applies forces to slow down the linear and angular velocity of an object. This is often used globally on the space to simulate air resistance, but can also be used for slowing movement in a water region, making one object slow down quickly, etc...

 #  Drag vs. Damping
DragEffect exposes properties for setting both drag and damping coefficients.

A drag force is defined as:

(NOTE) F = -//b//v

where v is the object's velocity and *b* is the drag coefficient. This is a linear drag approximation ([[https://en.wikipedia.org/wiki/Drag_(physics)#Very_low_Reynolds_numbers:_Stokes.27_drag | Stoke's drag]]) that applies a force opposite of the objects velocity. Valid values of b range from 0 to `1/dt` and can be through of as approximately how many seconds it'll take the object to stop when no other forces are applied.

Damping defines a drag __acceleration__ to be applied by the equation:

(NOTE) A = -//b//v

The only difference between drag and damping is whether the resultant acceleration takes the object's mass into account. Drag will slow down some objects more than others while damping will slow down all objects the same, regardless of mass.

Angular drag is defined similarly to linear drag as:

(NOTE) T = -kw

where `w` is the angular velocity, `k` is the angular drag coefficient, and `T` is the resultant torque. Angular damping similarly defines an angular acceleration instead of force.

 #  Application Modes
The DragEffect component is expected to work with all application modes. Drag applied to the space or level will affect all objects within. Used as a Region effect, drag will slow down all objects in contact with the Region. On a [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/RigidBody.markdown) the effect will slow down that object alone. [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/Colliders.markdown) and Hierarchy effects will behave the same as a RigidBody effect.

---
 #  Related Materials
 ##  Manual
- [physicseffectsandregions.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions.markdown)
- [RigidBody.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/RigidBody.markdown)
- [Colliders.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/Colliders.markdown)

 ##  Reference
- [DragEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/DragEffect.markdown)
- [PhysicsEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/PhysicsEffect.markdown)
- [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/RigidBody.markdown)
- [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/Collider.markdown)
- [Region](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/Region.markdown) 

 