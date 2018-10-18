 `Component` `Physics`



(NOTE) Represents a ball and socket joint. A position joint constrains the two anchor points on each object to be equal. Limits, motors, and springs typically should not be used. Add on definitions: Limit: A limit will provide a min/max translation on every axis (x,y,z) that the objects must be between. Motor: A motor will attempt to drive the translation in the positive direction on every axis. Spring: A spring will make the translation on every axis springy at the bounds.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/positionjoint.markdown#positionjoint-void)|[ LocalPointA](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/positionjoint.markdown#localpointa-zero-engine)|[joint](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/joint.markdown)| |
|[ SetWorldPoints](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/positionjoint.markdown#setworldpoints-void)|[ LocalPointB](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/positionjoint.markdown#localpointb-zero-engine)| | |
| |[ WorldPointA](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/positionjoint.markdown#worldpointa-zero-engine)| | |
| |[ WorldPointB](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/positionjoint.markdown#worldpointb-zero-engine)| | |


 #  Properties


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
 #  Methods


---  
 #  PositionJoint : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function PositionJoint()
> ``` 


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
 

 