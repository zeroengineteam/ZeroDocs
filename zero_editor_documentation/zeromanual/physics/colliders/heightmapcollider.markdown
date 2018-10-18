(NOTE) **Recommended Reading:** The [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown) page should be read before this page.

[HeightMapCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/heightmapcollider.markdown) defines collision for a [HeightMap](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/heightmap.markdown). Physics more efficiently represent collision for a HeightMap than a generic mesh.

NOTE: HeightMapCollider is assumed to be static and should not be used with a dynamic [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders/rigidbody.markdown).

 #  Thickness
HeightMapCollider exposes the Thickness  property to turn each triangle of the height map into a [prism](https://en.wikipedia.org/wiki/Triangular_prism ). This helps avoid tunneling with fast moving objects.

---
 #  Related Materials
 ##  Manual
 - [colliders.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown)
 - [rigidbody.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders/rigidbody.markdown)

 ##  Reference
 - [HeightMapCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/heightmapcollider.markdown)
 - [HeightMap](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/heightmap.markdown)
 - [RigidBody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown) 

 