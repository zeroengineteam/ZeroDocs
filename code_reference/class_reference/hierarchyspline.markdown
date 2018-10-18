 `Component` `Engine`



(NOTE) A spline that builds its control points from all child cogs that have Transforms.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ ForceRebuild](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/hierarchyspline.markdown#forcerebuild-void)|[ Closed](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/hierarchyspline.markdown#closed-zero-engine-docum)|[component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/component.markdown)| |
|[ Constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/hierarchyspline.markdown#hierarchyspline-void)|[ DebugDrawSpline](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/hierarchyspline.markdown#debugdrawspline-zero-eng)| | |
|[ RebuildIfModified](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/hierarchyspline.markdown#rebuildifmodified-void)|[ Error](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/hierarchyspline.markdown#error-zero-engine-docume)| | |
| |[ Spline](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/hierarchyspline.markdown#spline-zero-engine-docum)| | |
| |[ SplineColor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/hierarchyspline.markdown#splinecolor-zero-engine)| | |
| |[ SplineType](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/hierarchyspline.markdown#splinetype-zero-engine-d)| | |


 #  Properties


---  
 #  Closed : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Does the spline loop back on itself?
> ``` lang=cpp, name=Zilch
> var Closed : Boolean


---  
 #  DebugDrawSpline : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Should the spline draw every frame? Mainly used for debugging purposes.
> ``` lang=cpp, name=Zilch
> var DebugDrawSpline : Boolean


---  
 #  Error : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The max number of units that a line segment is allowed to deviate from the curve.
> ``` lang=cpp, name=Zilch
> var Error : Real


---  
 #  Spline : [spline](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/spline.markdown)

 `read-only`

> The internal spline data.
> ``` lang=cpp, name=Zilch
> var Spline : Spline


---  
 #  SplineColor : [real4](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real4.markdown)

> What color should that spline be drawn with.
> ``` lang=cpp, name=Zilch
> var SplineColor : Real4


---  
 #  SplineType : [SplineType](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#splinetype)

> The kind of spline (Linear, BSpline, CatmullRom). Determines how the control points affect the curve.
> ``` lang=cpp, name=Zilch
> var SplineType : SplineType


---  
 #  Methods


---  
 #  ForceRebuild : Void

> Forcibly rebuilds the baked points for the spline.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ForceRebuild()
> ``` 


---  
 #  HierarchySpline : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function HierarchySpline()
> ``` 


---  
 #  RebuildIfModified : Void

> Rebuild the baked points if there are any changes to the spline's control points. This should never need to be manually called.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function RebuildIfModified()
> ``` 


---  
 
  
  
  
  
  
  
  

 