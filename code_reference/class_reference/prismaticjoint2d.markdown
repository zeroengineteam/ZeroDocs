 `Component` `Physics`



(NOTE) A prismatic joint is used to create something similar to a piston. This is the 2d version of PrismaticJoint. This joint is used in 2d mode for increased performance and stability. The slider axis is projected onto the z axis (the z component is ignored) so that the objects can be arbitrarily far apart. The x and y rotations are also ignored since the objects are only allowed to rotate about the z axis. Add on definitions: Limit: A limit will provide a min/max translational distance for the two objects on the slider axis. Motor: A motor will push/pull the objects on the slider axis. Spring: A spring will make the slider axis springy at its limits.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/prismaticjoint2d.markdown#prismaticjoint2d-void)|[ LocalAxisA](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/prismaticjoint2d.markdown#localaxisa-zero-engine-d)|[joint](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/joint.markdown)| |
|[ SetWorldPoints](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/prismaticjoint2d.markdown#setworldpoints-void)|[ LocalAxisB](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/prismaticjoint2d.markdown#localaxisb-zero-engine-d)| | |
| |[ LocalBasisA](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/prismaticjoint2d.markdown#localbasisa-zero-engine)| | |
| |[ LocalBasisB](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/prismaticjoint2d.markdown#localbasisb-zero-engine)| | |
| |[ LocalPointA](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/prismaticjoint2d.markdown#localpointa-zero-engine)| | |
| |[ LocalPointB](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/prismaticjoint2d.markdown#localpointb-zero-engine)| | |
| |[ WorldAxis](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/prismaticjoint2d.markdown#worldaxis-zero-engine-do)| | |
| |[ WorldPointA](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/prismaticjoint2d.markdown#worldpointa-zero-engine)| | |
| |[ WorldPointB](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/prismaticjoint2d.markdown#worldpointb-zero-engine)| | |


 #  Properties


---  
 #  LocalAxisA : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The locally defined axis on object A . 
> ``` lang=cpp, name=Zilch
> var LocalAxisA : Real3


---  
 #  LocalAxisB : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The locally defined axis on object B . 
> ``` lang=cpp, name=Zilch
> var LocalAxisB : Real3


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
 #  WorldAxis : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The axis in world space that is being rotated about . 
> ``` lang=cpp, name=Zilch
> var WorldAxis : Real3


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
 #  PrismaticJoint2d : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function PrismaticJoint2d()
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
 

 