(NOTE) **Recommended Reading:** The [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown) page should be read before this page.

[ConvexMeshCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/convexmeshcollider.markdown) defines a [convex hull](https://en.wikipedia.org/wiki/Convex_hull ) for collision detection based upon a [ConvexMesh](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/convexmesh.markdown) resource.

WARNING: A future version will likely combine all physics mesh types together.

Unlike [MeshCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders/meshcollider.markdown), convex meshes have a volume which means inertia properties can be computed. ConvexMeshColliders are complex shapes that are still efficient for physics. They are commonly used with dynamic rigid bodies to create an object with a complicated surface.

If a mesh is non-convex, the convex hull of the shape is used for collision detection. This means that the geometry will be an approximation of the surface. 



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46628.png)


Pictured above is an illustration of the convex hull of an object. Note that the collision is bigger than the original shape.

---

 #  Related Materials
 ##  Manual
- [colliders.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown)
- [meshcollider.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders/meshcollider.markdown)
 ##  Reference
- [ConvexMeshCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/convexmeshcollider.markdown)
- [ConvexMesh](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/convexmesh.markdown)
- [MeshCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/meshcollider.markdown)
- [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collider.markdown) 

 