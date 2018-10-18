The [PhysicsSolverConfig](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicssolverconfig.markdown) resource allows a certain level of customization in how physics solves [PhysicsSolverPositionCorrection](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#physicssolverpositioncor) types.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47497.png)


WARNING: If you don't understand the topic of constraints then you probably shouldn't change the properties of this resource.

 #  Velocity Restitution Threshold: Collision vs. Contact
When performing collision resolution, physics has to distinguish between collisions and contacts. In this case, a collision refers to a large impact whereas a contact refers to a near resting contact. These are important to distinguish between when applying restitution; otherwise, resting objects will jitter. The physics solver uses this threshold value to compare against the relative velocity of the objects in contact. If the relative velocity is lower than this threshold then no restitution is applied.

 #  Iteration Count
Physics solvers are typically iterative in how they solve constraints (contacts, joints, etc...). The more iterations used the more stable a scene tends to be, but at the cost of decreased performance. Independent iteration counts are exposed for impulse solving and position solving (if configured to solve positions).

 #  Position Correction Type
Physics typically solves with discrete time-steps which allows position error to appear in joints. Zero's physics system provides two methods to fix position error:
 - **Baumgarte** fixes position error by applying a "penalty force". This typically produces constraints that feel soft and spongy.
 - **PostStabilization** fixes position error by solving the position constraints directly. This makes stiffer constraints but often at the cost of speed and occasionally stability.
 
This property configures the default solving method for all constraints unless overridden as described below.

 #  Joint/Contact Configurations
[JointConfigOverride](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/jointconfigoverride.markdown) component and uses its properties. Note that this component cannot be applied to contacts. Next, the joint will check its space's PhysicsSolverConfig to see if a block for its joint type exists. If this block exists then it'll use the specified values. Finally, any global fallback values will be used such as the position correction type. In the case of properties like slop, each joint type has its own defaults to use when no block exists.

 #  Joint Blocks
A configuration block can be added for any joint type that determines how the physics system solves that constraint type. This allows changing certain joint types at a global level to solve differently from others.

---

 #  Related Materials
 ##  Manual
- [joints.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/joints.markdown)
- [collisionoverview.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/collisionoverview.markdown)
- [physicsspace.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicsspace.markdown)

 ##  Code Reference
- [Joint](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/joint.markdown)
- [JointConfigOverride](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/jointconfigoverride.markdown)
- [ConstraintConfigBlock](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/constraintconfigblock.markdown)
- [PhysicsSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsspace.markdown)
- [PhysicsSolverPositionCorrection](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#physicssolverpositioncor) 

 