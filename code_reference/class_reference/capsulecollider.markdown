 `Component` `Physics`



(NOTE) Defines the collision volume for a capsule defined by a height and radius. A capsule can be thought of as a cylinder with spherical end caps.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/capsulecollider.markdown#capsulecollider-void)|[ Direction](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/capsulecollider.markdown#direction-zero-engine-do)|[collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collider.markdown)| |
| |[ Height](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/capsulecollider.markdown#height-zero-engine-docum)| | |
| |[ Radius](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/capsulecollider.markdown#radius-zero-engine-docum)| | |
| |[ ScalingMode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/capsulecollider.markdown#scalingmode-zero-engine)| | |
| |[ WorldCylinderHeight](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/capsulecollider.markdown#worldcylinderheight-zero)| | |
| |[ WorldRadius](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/capsulecollider.markdown#worldradius-zero-engine)| | |


 #  Properties


---  
 #  Direction : [AxisDirection](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#axisdirection)

> The direction that the height is defined along. Allows the user to change whether the capsule's height is along the local-space x, y, or z axis.
> ``` lang=cpp, name=Zilch
> var Direction : AxisDirection


---  
 #  Height : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The local space distance from the center of one sphere to another.
> ``` lang=cpp, name=Zilch
> var Height : Real


---  
 #  Radius : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The local space radius of the spheres at the capsule edges.
> ``` lang=cpp, name=Zilch
> var Radius : Real


---  
 #  ScalingMode : [CapsuleScalingMode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#capsulescalingmode)

> How should non-uniform scale affect the capsules size. Should a scale of 2 on the height axis double the total capsule size or should it double the capsule height?
> ``` lang=cpp, name=Zilch
> var ScalingMode : CapsuleScalingMode


---  
 #  WorldCylinderHeight : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

 `read-only`

> The full height of the capsule's cylinder after the scale is applied (world distance from one sphere to another).
> ``` lang=cpp, name=Zilch
> var WorldCylinderHeight : Real


---  
 #  WorldRadius : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

 `read-only`

> The radius of the sphere caps after scale is applied.
> ``` lang=cpp, name=Zilch
> var WorldRadius : Real


---  
 #  Methods


---  
 #  CapsuleCollider : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function CapsuleCollider()
> ``` 


---  
 

 