(NOTE) **Recommended Reading:** The [Collider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown) page should be read before this page.

[MeshCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/MeshCollider.markdown) defines a surface mesh for world geometry based upon a [PhysicsMesh](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/PhysicsMesh.markdown) resource.

WARNING: A future version will likely combine all physics mesh types together.

MeshCollider defines a surface for collision; there are no volume or inertia properties to be computed. This means that a MeshCollider is assumed to be static and should not be used in conjunction with a dynamic [RigidBody](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/colliders/RigidBody.markdown) (static is fine). The primary use of MeshCollider is to define static world geometry that is too complicated to represent in a more efficient way for physics.

NOTE: As MeshCollider is assumed to be static, collision detection is not performed between two MeshColliders. 

---
 #  Related Materials
 ##  Manual
- [colliders.markdown](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown)
- [RigidBody.markdown](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/colliders/RigidBody.markdown)

 ##  Reference
- [MeshCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/MeshCollider.markdown)
- [Collider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Collider.markdown)
- [RigidBody](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/RigidBody.markdown) 
  
  
  
  
  
  
  

 