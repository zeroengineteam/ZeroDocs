The [ForceEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/forceeffect.markdown) and [GravityEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gravityeffect.markdown) components are direction effects that apply linear forces to push an object in a direction.

The only difference between the gravity and force effect is whether an acceleration or force is applied. A GravityEffect will apply a constant acceleration to an object, i.e. the object's mass will not affect the acceleration. ForceEffect will take the object's mass into account. The rest of this page will use *force* to refer to the acceleration or force depending on the effect type attached.

The *force// applied is a constant linear //force* based upon the direction and strength of the effect. By default, the effect will be applied in the local space of the object it's attached to. This means that rotating the object will affect the direction of the //force//.

 #  Application Methods
GravityEffect and ForceEffect are assumed to work with all application methods of PhysicsEffects. If the effect is on the Space or LevelSettings then the *force* will apply to all objects in the level. If the effect is on a Region then it'll apply to all objects in the region. Otherwise, the effect will apply to the center of mass of the [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/rigidbody.markdown) (no angular //force//). [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/colliders.markdown) and Hierarchy application methods do not differ from the RigidBody mode.

---
 #  Related Materials
 ##  Manual
- [physicseffectsandregions.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions.markdown)
- [rigidbody.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/rigidbody.markdown)
- [colliders.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/colliders.markdown)

 ##  Reference
- [ForceEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/forceeffect.markdown)
- [GravityEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/gravityeffect.markdown)
- [PhysicsEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicseffect.markdown)
- [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown)
- [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collider.markdown) 

 