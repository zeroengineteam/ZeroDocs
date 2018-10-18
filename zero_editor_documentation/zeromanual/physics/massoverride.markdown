By default, a [MassOverride](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/massoverride.markdown) component is used to override these values. There's two primary uses for mass override: to lock the mass and to set the mass.

MassOverride is commonly used to save the mass values of a RigidBody. During game development, the size of objects may need to be altered while keeping behavior the same. Unfortunately, the size of a collider is used to compute the mass of a RigidBody. To help alleviate this, the MassOverride component can be used to save a RigidBody's current mass properties regardless of all attached colliders and materials. This cached mass can be re-computed at any time from the current RigidBody's values.

Another common use of MassOverride is to manually set the mass. Sometimes the user wants to tweak an object's mass without changing size or altering a material. This can be achieved through the Mass  property. It is important to note that mass is represented by linear and angular (inertia tensor) values. Tweaking the mass will currently apply a ratio change to the inertia tensor, which is only exposed via script for now. Large alterations to the mass property can have undesired effects on rotation.

---
 #  Related Materials
 ##  Manual
- [rigidbody.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/rigidbody.markdown)
- [colliders.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown)
 ##  Reference
- [MassOverride](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/massoverride.markdown)
- [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown)
- [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collider.markdown) 

 