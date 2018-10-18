(NOTE) **Recommended Reading:** The [Collider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown) page should be read before this page.

[MultiConvexMeshCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/MultiConvexMeshCollider.markdown) defines a collection of [convex hulls](https://en.wikipedia.org/wiki/Convex_hull ) for collision detection based upon a [MultiConvexMesh](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/MultiConvexMesh.markdown) resource.

WARNING: A future version will likely combine all physics mesh types together.

MultiConvexMeshCollider allows more complicated shapes to be represented than a [ConvexMeshCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/colliders/ConvexMeshCollider.markdown) while still retaining performance. Physics needs convex shapes for efficiency so this Collider represents non-convex shapes as a collection of sub convex meshes.

Currently, the editor for this mesh type only works for 2D shapes (sprites). 3D meshes can be made, but only through script. Future plans include implementing 3D approximate convex decomposition.

 #  Troubleshooting
As the MultiConvexMeshCollider contains multiple convex pieces, seams can exist between the pieces. This can cause [edge catching](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/colliders/PhysicsTroubleshooting/EdgeCatching.markdown) issues when objects slide across the surface. Additionally, an object can get sandwiched in the interior between two sub-meshes.

---

 #  Related Materials
 ##  Manual
- [colliders.markdown](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown)
- [ConvexMeshCollider.markdown](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/colliders/ConvexMeshCollider.markdown)
- [EdgeCatching.markdown](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/colliders/PhysicsTroubleshooting/EdgeCatching.markdown)
 ##  Reference
- [MultiConvexMeshCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/MultiConvexMeshCollider.markdown)
- [MultiConvexMesh](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/MultiConvexMesh.markdown)
- [ConvexMeshCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/ConvexMeshCollider.markdown)
- [Collider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Collider.markdown) 
  
  
  
  
  
  
  

 