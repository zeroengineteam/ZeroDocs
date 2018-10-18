 `Component` `Physics`



(NOTE) Defines the collision volume of a box defined by a size on each axis.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/boxcollider.markdown#boxcollider-void)|[ HalfSize](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/boxcollider.markdown#halfsize-zero-engine-doc)|[collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collider.markdown)| |
| |[ Size](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/boxcollider.markdown#size-zero-engine-documen)| | |
| |[ WorldSize](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/boxcollider.markdown#worldsize-zero-engine-do)| | |


 #  Properties


---  
 #  HalfSize : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The half size (from the center to the upper-right corner) on each axis of the box in local space. Used to make the box's size match a model or some other volume without needing to scale the transform (also avoids non-uniform scale issues).
> ``` lang=cpp, name=Zilch
> var HalfSize : Real3


---  
 #  Size : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The size (from min to max) on each axis of the box in local space. Used to make the box's size match a model or some other volume without needing to scale the transform (also avoids non-uniform scale issues).
> ``` lang=cpp, name=Zilch
> var Size : Real3


---  
 #  WorldSize : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

 `read-only`

> The size of the box after the transform is applied (scale and rotation).
> ``` lang=cpp, name=Zilch
> var WorldSize : Real3


---  
 #  Methods


---  
 #  BoxCollider : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function BoxCollider()
> ``` 


---  
 

 