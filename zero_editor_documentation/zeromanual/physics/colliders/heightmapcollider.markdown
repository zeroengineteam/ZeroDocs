(NOTE) **Recommended Reading:** The [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown) page should be read before this page.

[HeightMapCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/HeightMapCollider.markdown) defines collision for a [HeightMap](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/HeightMap.markdown). Physics more efficiently represent collision for a HeightMap than a generic mesh.

NOTE: HeightMapCollider is assumed to be static and should not be used with a dynamic [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders/RigidBody.markdown).

 #  Thickness
HeightMapCollider exposes the Thickness  property to turn each triangle of the height map into a [prism](https://en.wikipedia.org/wiki/Triangular_prism ). This helps avoid tunneling with fast moving objects.

---
 #  Related Materials
 ##  Manual
 - [colliders.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown)
 - [RigidBody.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders/RigidBody.markdown)

 ##  Reference
 - [HeightMapCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/HeightMapCollider.markdown)
 - [HeightMap](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/HeightMap.markdown)
 - [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/RigidBody.markdown) 

 