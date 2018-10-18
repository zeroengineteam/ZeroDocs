[CylinderCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cylindercollider.markdown) defines a [cylindrical](https://en.wikipedia.org/wiki/Cylinder ) shape for collision. The base size of the cylinder is determined by the Radius  and Height  properties. Scale is applied afterwards to determine the final cylinder's size.

(NOTE) **Recommended Reading:** The [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown) page should be read before this page.


 #  Radius
Radius  defines the radius of the cylinder in local space.

 #  Height
Height  defines the total local space height of the cylinder. The height is defined as the distance from the bottom disc to the top disc.

 #  Direction
The Direction enum property is used to configure which local-space axis the height of the cylinder runs along. This allows aligning a cylinder with an asset that was configured about a different axis.

 #  Non-Uniform Scale
When non-uniform scale is applied, the CylinderCollider will always stay a perfect cylinder. The height of the cylinder will fully respect the object's scale, but the radius will come from the larger of the two remaining scale values.


---
 #  Related Materials
 ##  Manual
- [colliders.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown)

 ##  Reference
- [CylinderCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cylindercollider.markdown)
- [Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collider.markdown) 

 