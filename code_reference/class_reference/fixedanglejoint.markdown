 `Component` `Physics`



(NOTE) Locks the orientation of two objects together. Used when two objects should always rotate in unison. Typically not used by itself, but useful as a proof of concept for joints that use this functionality internally. Limits, motors, and springs should most likely not be used on this. Add on definitions: Limit: A limit will provide a min/max angle on every axis that the objects must be between. Motor: A motor will attempt to drive the rotation on every axis forward. Spring: A spring will make the rotations on every axis at the bounds springy.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/fixedanglejoint.markdown#fixedanglejoint-void)|[ LocalBasisA](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/fixedanglejoint.markdown#localbasisa-zero-engine)|[joint](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/joint.markdown)| |
| |[ LocalBasisB](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/fixedanglejoint.markdown#localbasisb-zero-engine)| | |


 #  Properties


---  
 #  LocalBasisA : [quaternion](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/quaternion.markdown)

> The local space reference frame of object A . This frame is transformed to world space and then aligned with object B s frame . 
> ``` lang=cpp, name=Zilch
> var LocalBasisA : Quaternion


---  
 #  LocalBasisB : [quaternion](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/quaternion.markdown)

> The local space reference frame of object B . This frame is transformed to world space and then aligned with object A s frame . 
> ``` lang=cpp, name=Zilch
> var LocalBasisB : Quaternion


---  
 #  Methods


---  
 #  FixedAngleJoint : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function FixedAngleJoint()
> ``` 


---  
 

 