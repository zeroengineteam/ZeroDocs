(NOTE) **Recommended Reading:** The [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown) page should be read before this page.

[MeshCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/meshcollider.markdown) defines a surface mesh for world geometry based upon a [PhysicsMesh](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsmesh.markdown) resource.

WARNING: A future version will likely combine all physics mesh types together.

MeshCollider defines a surface for collision; there are no volume or inertia properties to be computed. This means that a MeshCollider is assumed to be static and should not be used in conjunction with a dynamic [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders/rigidbody.markdown) (static is fine). The primary use of MeshCollider is to define static world geometry that is too complicated to represent in a more efficient way for physics.

NOTE: As MeshCollider is assumed to be static, collision detection is not performed between two MeshColliders. 

---
 #  Related Materials
 ##  Manual
- [colliders.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown)
- [rigidbody.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders/rigidbody.markdown)

 ##  Reference
- [MeshCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/meshcollider.markdown)
- [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collider.markdown)
- [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown) 

 