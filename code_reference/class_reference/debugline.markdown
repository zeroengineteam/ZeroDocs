 `Geometry`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugline.markdown#debugline-void)|[ BoxHeads](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugline.markdown#boxheads-zero-engine-doc)| | |
| |[ Color](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugline.markdown#color-zero-engine-docume)| | |
| |[ DualHeads](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugline.markdown#dualheads-zero-engine-do)| | |
| |[ End](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugline.markdown#end-zero-engine-document)| | |
| |[ Filled](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugline.markdown#filled-zero-engine-docum)| | |
| |[ HeadSize](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugline.markdown#headsize-zero-engine-doc)| | |
| |[ OnTop](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugline.markdown#ontop-zero-engine-docume)| | |
| |[ Start](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugline.markdown#start-zero-engine-docume)| | |
| |[ ViewAligned](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugline.markdown#viewaligned-zero-engine)| | |
| |[ ViewScaled](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugline.markdown#viewscaled-zero-engine-d)| | |
| |[ ViewScaleOffset](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/debugline.markdown#viewscaleoffset-zero-eng)| | |


 #  Properties


---  
 #  BoxHeads : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> ``` lang=cpp, name=Zilch
> var BoxHeads : Boolean


---  
 #  Color : [real4](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real4.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Color : Real4


---  
 #  DualHeads : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> ``` lang=cpp, name=Zilch
> var DualHeads : Boolean


---  
 #  End : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> 
> ``` lang=cpp, name=Zilch
> var End : Real3


---  
 #  Filled : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Filled : Boolean


---  
 #  HeadSize : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> 
> ``` lang=cpp, name=Zilch
> var HeadSize : Real


---  
 #  OnTop : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> ``` lang=cpp, name=Zilch
> var OnTop : Boolean


---  
 #  Start : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Start : Real3


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
 #  DebugLine : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function DebugLine()
> ``` 


---  
 #  DebugLine : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |ray|[ray](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/ray.markdown)| |
> ``` lang=cpp, name=Zilch
> function DebugLine(ray : Ray)
> ``` 


---  
 #  DebugLine : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |ray|[ray](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/ray.markdown)| |
> |t|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function DebugLine(ray : Ray, t : Real)
> ``` 


---  
 #  DebugLine : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |start|[real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> |end|[real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function DebugLine(start : Real3, end : Real3)
> ``` 


---  
 #  DebugLine : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |start|[real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> |end|[real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> |headSize|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function DebugLine(start : Real3, end : Real3, headSize : Real)
> ``` 


---  
 #  DebugLine : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |segment|[segment](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/segment.markdown)| |
> ``` lang=cpp, name=Zilch
> function DebugLine(segment : Segment)
> ``` 


---  
 

 