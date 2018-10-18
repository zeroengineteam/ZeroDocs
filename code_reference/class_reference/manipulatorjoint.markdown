 `Component` `Physics`



(NOTE) Legacy. A position joint that is designed to manipulate one object. The only difference between this and the position joint is that the manipulator always draws itself, draws differently, and configures the max impulse differently.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/manipulatorjoint.markdown#manipulatorjoint-void)|[ LocalPoint](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/manipulatorjoint.markdown#localpoint-zero-engine-d)|[joint](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/joint.markdown)| |
| |[ TargetPoint](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/manipulatorjoint.markdown#targetpoint-zero-engine)| | |
| |[ WorldPoint](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/manipulatorjoint.markdown#worldpoint-zero-engine-d)| | |


 #  Properties


---  
 #  LocalPoint : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The local space point on the object that the joint is connected to.
> ``` lang=cpp, name=Zilch
> var LocalPoint : Real3


---  
 #  TargetPoint : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The point in world space that the object's point is being moved towards.
> ``` lang=cpp, name=Zilch
> var TargetPoint : Real3


---  
 #  WorldPoint : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The world space point on the object that the joint is connected to.
> ``` lang=cpp, name=Zilch
> var WorldPoint : Real3


---  
 #  Methods


---  
 #  ManipulatorJoint : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ManipulatorJoint()
> ``` 


---  
 

 