(NOTE) **Recommended Reading:** The [Collider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown) page should be read before this page.

[ConvexMeshCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/ConvexMeshCollider.markdown) defines a [convex hull](https://en.wikipedia.org/wiki/Convex_hull ) for collision detection based upon a [ConvexMesh](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/ConvexMesh.markdown) resource.

WARNING: A future version will likely combine all physics mesh types together.

Unlike [MeshCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/colliders/MeshCollider.markdown), convex meshes have a volume which means inertia properties can be computed. ConvexMeshColliders are complex shapes that are still efficient for physics. They are commonly used with dynamic rigid bodies to create an object with a complicated surface.

If a mesh is non-convex, the convex hull of the shape is used for collision detection. This means that the geometry will be an approximation of the surface. 



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46628.png)


Pictured above is an illustration of the convex hull of an object. Note that the collision is bigger than the original shape.

---

 #  Related Materials
 ##  Manual
- [colliders.markdown](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown)
- [MeshCollider.markdown](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/colliders/MeshCollider.markdown)
 ##  Reference
- [ConvexMeshCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/ConvexMeshCollider.markdown)
- [ConvexMesh](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/ConvexMesh.markdown)
- [MeshCollider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/MeshCollider.markdown)
- [Collider](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Collider.markdown) 
  
  
  
  
  
  
  

 