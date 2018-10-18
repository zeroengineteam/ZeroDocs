 `Geometry`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugcylinder.markdown#debugcylinder-void)|[ Color](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugcylinder.markdown#color-zero-engine-docume)| | |
| |[ End](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugcylinder.markdown#end-zero-engine-document)| | |
| |[ OnTop](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugcylinder.markdown#ontop-zero-engine-docume)| | |
| |[ Radius](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugcylinder.markdown#radius-zero-engine-docum)| | |
| |[ Start](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugcylinder.markdown#start-zero-engine-docume)| | |
| |[ ViewAligned](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugcylinder.markdown#viewaligned-zero-engine)| | |
| |[ ViewScaled](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugcylinder.markdown#viewscaled-zero-engine-d)| | |
| |[ ViewScaleOffset](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/debugcylinder.markdown#viewscaleoffset-zero-eng)| | |


 #  Properties


---  
 #  Color : [real4](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Color : Real4


---  
 #  End : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> 
> ``` lang=cpp, name=Zilch
> var End : Real3


---  
 #  OnTop : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> 
> ``` lang=cpp, name=Zilch
> var OnTop : Boolean


---  
 #  Radius : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Radius : Real


---  
 #  Start : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Start : Real3


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
 #  DebugCylinder : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function DebugCylinder()
> ``` 


---  
 #  DebugCylinder : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |start|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |end|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |radius|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function DebugCylinder(start : Real3, end : Real3, radius : Real)
> ``` 


---  
 #  DebugCylinder : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |position|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |axis|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |height|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |radius|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function DebugCylinder(position : Real3, axis : Real3, height : Real, radius : Real)
> ``` 


---  
 

 