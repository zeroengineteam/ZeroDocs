 `Geometry`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugbox.markdown#debugbox-void)|[ Color](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugbox.markdown#color-zero-engine-docume)| | |
| |[ Filled](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugbox.markdown#filled-zero-engine-docum)| | |
| |[ HalfExtents](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugbox.markdown#halfextents-zero-engine)| | |
| |[ OnTop](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugbox.markdown#ontop-zero-engine-docume)| | |
| |[ Position](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugbox.markdown#position-zero-engine-doc)| | |
| |[ Rotation](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugbox.markdown#rotation-zero-engine-doc)| | |
| |[ ViewAligned](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugbox.markdown#viewaligned-zero-engine)| | |
| |[ ViewScaled](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugbox.markdown#viewscaled-zero-engine-d)| | |
| |[ ViewScaleOffset](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugbox.markdown#viewscaleoffset-zero-eng)| | |


 #  Properties


---  
 #  Color : [real4](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Color : Real4


---  
 #  Filled : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Filled : Boolean


---  
 #  HalfExtents : [real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)

> 
> ``` lang=cpp, name=Zilch
> var HalfExtents : Real2


---  
 #  OnTop : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> 
> ``` lang=cpp, name=Zilch
> var OnTop : Boolean


---  
 #  Position : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Position : Real3


---  
 #  Rotation : [quaternion](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/quaternion.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Rotation : Quaternion


---  
 #  ViewAligned : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> 
> ``` lang=cpp, name=Zilch
> var ViewAligned : Boolean


---  
 #  ViewScaled : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> 
> ``` lang=cpp, name=Zilch
> var ViewScaled : Boolean


---  
 #  ViewScaleOffset : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> 
> ``` lang=cpp, name=Zilch
> var ViewScaleOffset : Real3


---  
 #  Methods


---  
 #  DebugBox : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function DebugBox()
> ``` 


---  
 #  DebugBox : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |aabb|[aabb](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/aabb.markdown)| |
> ``` lang=cpp, name=Zilch
> function DebugBox(aabb : Aabb)
> ``` 


---  
 #  DebugBox : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |position|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |halfExtents|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function DebugBox(position : Real3, halfExtents : Real)
> ``` 


---  
 #  DebugBox : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |position|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |halfExtents|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |rotation|[quaternion](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/quaternion.markdown)| |
> ``` lang=cpp, name=Zilch
> function DebugBox(position : Real3, halfExtents : Real, rotation : Quaternion)
> ``` 


---  
 #  DebugBox : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |position|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |halfExtents|[real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)| |
> ``` lang=cpp, name=Zilch
> function DebugBox(position : Real3, halfExtents : Real2)
> ``` 


---  
 #  DebugBox : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |position|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |halfExtents|[real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)| |
> |rotation|[quaternion](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/quaternion.markdown)| |
> ``` lang=cpp, name=Zilch
> function DebugBox(position : Real3, halfExtents : Real2, rotation : Quaternion)
> ``` 


---  
 

 