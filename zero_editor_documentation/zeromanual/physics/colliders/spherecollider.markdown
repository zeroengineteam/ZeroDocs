[SphereCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spherecollider.markdown) defines a [sphere](https://en.wikipedia.org/wiki/Sphere ) shape for collision. The size of the sphere is determined byRadius  and the Transform's Scale .

(NOTE) **Recommended Reading:** The [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown) page should be read before this page.

 #  Radius
A SphereCollider exposes the Radius  property which determines the pre-transform radius of the sphere. The SphereCollider will always be a perfect sphere, even when non-uniform scale is present. It does this by taking the largest scale value to determine the radius in world-space.

---
 ##  Related Materials
 ###  Manual
- [colliders.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown)

 ###  Reference
- [SphereCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spherecollider.markdown)
- [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collider.markdown) 

 