 `Geometry`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugobb.markdown#debugobb-void)|[ Color](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugobb.markdown#color-zero-engine-docume)| | |
| |[ Corners](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugobb.markdown#corners-zero-engine-docu)| | |
| |[ Filled](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugobb.markdown#filled-zero-engine-docum)| | |
| |[ HalfExtents](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugobb.markdown#halfextents-zero-engine)| | |
| |[ OnTop](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugobb.markdown#ontop-zero-engine-docume)| | |
| |[ Position](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugobb.markdown#position-zero-engine-doc)| | |
| |[ Rotation](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugobb.markdown#rotation-zero-engine-doc)| | |
| |[ ViewAligned](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugobb.markdown#viewaligned-zero-engine)| | |
| |[ ViewScaled](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugobb.markdown#viewscaled-zero-engine-d)| | |
| |[ ViewScaleOffset](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugobb.markdown#viewscaleoffset-zero-eng)| | |


 #  Properties


---  
 #  Color : [real4](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real4.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Color : Real4


---  
 #  Corners : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Corners : Boolean


---  
 #  Filled : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Filled : Boolean


---  
 #  HalfExtents : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> 
> ``` lang=cpp, name=Zilch
> var HalfExtents : Real3


---  
 #  OnTop : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> ``` lang=cpp, name=Zilch
> var OnTop : Boolean


---  
 #  Position : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Position : Real3


---  
 #  Rotation : [quaternion](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/quaternion.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Rotation : Quaternion


---  
 #  ViewAligned : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> ``` lang=cpp, name=Zilch
> var ViewAligned : Boolean


---  
 #  ViewScaled : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> ``` lang=cpp, name=Zilch
> var ViewScaled : Boolean


---  
 #  ViewScaleOffset : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> 
> ``` lang=cpp, name=Zilch
> var ViewScaleOffset : Real3


---  
 #  Methods


---  
 #  DebugObb : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function DebugObb()
> ``` 


---  
 #  DebugObb : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |aabb|[aabb](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/aabb.markdown)| |
> ``` lang=cpp, name=Zilch
> function DebugObb(aabb : Aabb)
> ``` 


---  
 #  DebugObb : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |position|[real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> |halfExtents|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function DebugObb(position : Real3, halfExtents : Real)
> ``` 


---  
 #  DebugObb : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |position|[real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> |halfExtents|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |rotation|[quaternion](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/quaternion.markdown)| |
> ``` lang=cpp, name=Zilch
> function DebugObb(position : Real3, halfExtents : Real, rotation : Quaternion)
> ``` 


---  
 #  DebugObb : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |position|[real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> |halfExtents|[real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function DebugObb(position : Real3, halfExtents : Real3)
> ``` 


---  
 #  DebugObb : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |position|[real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> |halfExtents|[real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> |rotation|[quaternion](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/quaternion.markdown)| |
> ``` lang=cpp, name=Zilch
> function DebugObb(position : Real3, halfExtents : Real3, rotation : Quaternion)
> ``` 


---  
 #  DebugObb : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |position|[real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> |halfExtents|[real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> |rotation|[real3x3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3x3.markdown)| |
> ``` lang=cpp, name=Zilch
> function DebugObb(position : Real3, halfExtents : Real3, rotation : Real3x3)
> ``` 


---  
 

 