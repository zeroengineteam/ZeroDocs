 `Component` `Physics`



(NOTE) Legacy. A linear axis joint is used to keep an object locked on a plane that is defined by a normal. This was made to help make a dynamic character controller. Instead of locking translation along a plane, the constraint can be turned off with a motor attached to it which will drive movement in the direction of the plane normal. This can then be thought of as a "move in direction" constraint.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/linearaxisjoint.markdown#linearaxisjoint-void)|[ WorldAxis](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/linearaxisjoint.markdown#worldaxis-zero-engine-do)|[joint](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/joint.markdown)| |


 #  Properties


---  
 #  WorldAxis : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The axis in world space that is constrained.
> ``` lang=cpp, name=Zilch
> var WorldAxis : Real3


---  
 #  Methods


---  
 #  LinearAxisJoint : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function LinearAxisJoint()
> ``` 


---  
 

 