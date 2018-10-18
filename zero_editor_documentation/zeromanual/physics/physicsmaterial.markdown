A [PhysicsMaterial](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsmaterial.markdown) describes material properties to use for a [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown). These properties affect how collisions are resolved between collider types.

Some PhysicsMaterial properties are used to define the surface of an object. In reality, these surface properties are not defined per object, but per object pair. The physics system computes a combined value for these properties as an approximation of the real life values.

 #  Density
Density  is used to compute a Collider's mass. This mass contributes to a {icon university}[[../RigidBody | RigidBody's]] total mass. Mass is computed as:

(NOTE) mass = density * volume

Physics uses density so mass is auto-computed when colliders change size. This is partially due to people having bad intuition for how mass scales.

Sometimes a Collider should not contribute a mass for accumulation on a RigidBody. In this case the density can be manually set to `0`.

 #  Restitution
Restitution  is a value typically in the range of `0` to `1` that determines how much energy in a collision is lost in the direction of the normal. Commonly this is thought of as how *bouncy* a surface is. A restitution of `0` signifies that all energy should be lost, i.e. no bounce. A restitution of `1` signifies that no energy should be lost, i.e. a perfect bounce. Values larger than `1` can be set to add energy but is not recommended.

The combined restitution is computed as the max of the two restitution values.

 #  Friction
Friction  determines how much energy in a collision is lost in the plane of the collision (the plane tangent to the collision normal). The upper bound of the friction force is computed as: `F=u*N`

where `N` is the total force in the normal direction and `u` is the friction scalar. Currently, dynamic and static friction are set to be equal.

The **combined friction** is computed as the square-root of the product of the two values, i.e. `F=sqrt(Fa*Fb)`.


 #  Restitution Importance
RestitutionImportance  determines which object's restitution should be used in collision resolution. When two objects are colliding, the restitution of the object with the higher importance value will be used. If both objects have the same importance value, the max of the two restitutions is applied.

 #  Friction Importance
FrictionImportance  determines which object's friction should be used in collision resolution. When two objects are colliding, the friction of the object with the higher importance value will be used. If both objects have the same importance value, the combined friction is used (see [above](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicsmaterial/.markdown#friction)).

---

 #  Related Materials
 ##  Manual
- [rigidbody.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/rigidbody.markdown)
- [colliders.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown)
 ##  Reference
- [PhysicsMaterial](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsmaterial.markdown)
- [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown)
- [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collider.markdown)
 

 