 `Component` `Physics`



(NOTE) A joint that models a wheel with shocks. This is the 2d version of WheelJoint. This joint is used in 2d mode for increased performance and stability. The motor axis is automatically set to the z axis, as that is the only axis objects can rotate about. Also, the translation on the z axis is ignored so that objects can be arbitrarily far apart. Add on definitions: Limit: A limit will provide a min/max angle on the motor axis. Motor: A motor will turn the objects about the motor axis. Spring: A spring will make the shock axis springy. A spring is attached by default to a wheel.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ SetWorldPoints](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/wheeljoint2d.markdown#setworldpoints-void)|[ LocalBasisA](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/wheeljoint2d.markdown#localbasisa-zero-engine)|[joint](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/joint.markdown)| |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/wheeljoint2d.markdown#wheeljoint2d-void)|[ LocalBasisB](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/wheeljoint2d.markdown#localbasisb-zero-engine)| | |
| |[ LocalPointA](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/wheeljoint2d.markdown#localpointa-zero-engine)| | |
| |[ LocalPointB](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/wheeljoint2d.markdown#localpointb-zero-engine)| | |
| |[ ShockAxis](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/wheeljoint2d.markdown#shockaxis-zero-engine-do)| | |
| |[ WorldPointA](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/wheeljoint2d.markdown#worldpointa-zero-engine)| | |
| |[ WorldPointB](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/wheeljoint2d.markdown#worldpointb-zero-engine)| | |
| |[ WorldShockAxis](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/wheeljoint2d.markdown#worldshockaxis-zero-engi)| | |


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
 #  LocalPointA : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The local point of the anchor on object A . 
> ``` lang=cpp, name=Zilch
> var LocalPointA : Real3


---  
 #  LocalPointB : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The local point of the anchor on object B . 
> ``` lang=cpp, name=Zilch
> var LocalPointB : Real3


---  
 #  ShockAxis : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The shock axis of the wheel in object A's local space.
> ``` lang=cpp, name=Zilch
> var ShockAxis : Real3


---  
 #  WorldPointA : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The position of the anchor on object A given a position in world space 
> ``` lang=cpp, name=Zilch
> var WorldPointA : Real3


---  
 #  WorldPointB : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The position of the anchor on object B given a position in world space 
> ``` lang=cpp, name=Zilch
> var WorldPointB : Real3


---  
 #  WorldShockAxis : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The shock axis of the wheel in world space.
> ``` lang=cpp, name=Zilch
> var WorldShockAxis : Real3


---  
 #  Methods


---  
 #  SetWorldPoints : Void

> Sets the position of the anchor on object A and B given a position in world space 
> |Name|Type|Description|
> |---|---|---|
> |point|[real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetWorldPoints(point : Real3)
> ``` 


---  
 #  WheelJoint2d : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function WheelJoint2d()
> ``` 


---  
 

 