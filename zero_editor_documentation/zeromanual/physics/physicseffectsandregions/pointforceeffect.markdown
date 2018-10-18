[PointGravityEffect](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/PointGravityEffect.markdown) and [PointForceEffect](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/PointForceEffect.markdown) are effects that apply linear forces towards a central point based upon an inner and outer strength. This is commonly used to create spherical effects such as planetary gravity or explosive shockwaves.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46383.png)


There's two main differences between the PointGravityEffect and PointForceEffect. The first is whether a positive strength points inwards or outwards. PointGravityEffect points inwards with a positive strength while PointForceEffect points outwards. The other difference is whether the applied *force// is actually a force or an acceleration. PointGravityEffect applies an acceleration to objects, i.e. the resultant acceleration is independent of the object's mass. PointForceEffect applies a force to object, i.e. the object's mass is taken into account. The rest of this page will use //force* to refer to the acceleration or force depending on the effect type attached.

The center of a point force's effect is the object's translation by default. This position can be moved with {nav icon=pencil-square-o, name="LocalPositionOffset"}, typically to align the position with some visual center on the object.

 #  Effect Interpolation
The *force* applied to an object is always linear (no angular //force//) and is computed as an interpolation between the two strength values based upon the object's distance from the effect's center. This is best illustrated with some graphs.


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46385.png)

When the distance is less than {nav icon=pencil-square-o, name="MinDistance"}, the effect will always apply {nav icon=pencil-square-o, name="MinStrength"} as a constant *force// value. When in-between the min and max distance values, the //force* will be an interpolation between the min and max strength values. Linear interpolation is pictured above. 


![QuadraticNoEffect](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46390.png)

Quadratic interpolation can also be used for smoother interpolation.



![QuadraticNoEffect](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46390.png)

When the distance from the effect center is beyond {nav icon=pencil-square-o, name="MaxDistance"}, how the effect is computed is based upon the {nav icon=list, name="EndCondition"} property. The `NoEffect` value will not apply any *force* beyond {nav icon=pencil-square-o, name="MaxDistance"}.



![QuadraticClampToMax](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46389.png)

`ClampToMax` will always apply {nav icon=pencil-square-o, name="MaxStrength"} regardless of how far away the object is.



![QuadraticContinueFalloff](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46392.png)

`ContinueFalloff` will extrapolate the curve beyond {nav icon=pencil-square-o, name="MaxDistance"} using the interpolation method specified by {nav icon=list, name="InterpolationMode"}.

NOTE: a *force* is only computed if the effect's Collider has collision, regardless of {nav icon=list, name="EndCondition's"} value.


With the two ring strength values it's possible to make a wide variety of point effects. Some possibilities include:
 - A standard gravity can be made by setting the inner strength larger than the outer strength.
 - The two effects can be set with opposite signs so as to attract to the center of the ring instead of the effect's center. 
 - An explosion can be made by setting the inner ring's strength large than the other ring's.

 #  Application Modes
Point effects are only expected to be used as Region effects. Other application modes are undefined.

---
 #  Related Materials
 ###  Manual
- [physicseffectsandregions.markdown](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/physicseffectsandregions.markdown)
 ##  Reference
- [PointForceEffect](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/PointForceEffect.markdown)
- [PointGravityEffect](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/PointGravityEffect.markdown)
- [PhysicsEffect](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/PhysicsEffect.markdown)
- [Region](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/Region.markdown)
- [PhysicsEffectInterpolationType](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#physicseffectinterpolationtype) 

 