 `Engine`

(NOTE) A spline built from control points. Bakes out the curve using an error term (distance from actual spline). Provides an interface to sample the curve at a given arc-length distance in order to provide constant speed interpolation.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Clone](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spline.markdown#clone-zero-engine-docume)|[ BakedPoints](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spline.markdown#bakedpoints-zero-engine)|[referencecountedeventobject](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/referencecountedeventobject.markdown)| |
|[ Create](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spline.markdown#create-zero-engine-docum)|[ Closed](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spline.markdown#closed-zero-engine-docum)| | |
|[ DebugDraw](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spline.markdown#debugdraw-void)|[ ControlPoints](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spline.markdown#controlpoints-zero-engin)| | |
|[ ForceRebuild](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spline.markdown#forcerebuild-void)|[ Error](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spline.markdown#error-zero-engine-docume)| | |
|[ RebuildIfModified](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spline.markdown#rebuildifmodified-void)|[ SplineType](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spline.markdown#splinetype-zero-engine-d)| | |
|[ SampleDistance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spline.markdown#sampledistance-zero-engi)|[ TotalDistance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spline.markdown#totaldistance-zero-engin)| | |
|[ SampleNormalized](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spline.markdown#samplenormalized-zero-en)| | | |


 #  Properties


---  
 #  BakedPoints : [splinebakedpoints](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splinebakedpoints.markdown)

 `read-only`

> The read-only curve points baked out to line segments using the provided error.
> ``` lang=cpp, name=Zilch
> var BakedPoints : SplineBakedPoints


---  
 #  Closed : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Does the spline loop back on itself?
> ``` lang=cpp, name=Zilch
> var Closed : Boolean


---  
 #  ControlPoints : [splinecontrolpoints](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splinecontrolpoints.markdown)

 `read-only`

> The control points used to bake out the curve.
> ``` lang=cpp, name=Zilch
> var ControlPoints : SplineControlPoints


---  
 #  Error : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The max number of units that a line segment is allowed to deviate from the curve.
> ``` lang=cpp, name=Zilch
> var Error : Real


---  
 #  SplineType : [SplineType](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#splinetype)

> The kind of spline (Linear, BSpline, CatmullRom). Determines how the control points affect the curve.
> ``` lang=cpp, name=Zilch
> var SplineType : SplineType


---  
 #  TotalDistance : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

 `read-only`

> The total arc-length of the curve. Use to normalize the curve if you wish.
> ``` lang=cpp, name=Zilch
> var TotalDistance : Real


---  
 #  Methods


---  
 #  Clone : [spline](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spline.markdown)

> Create a new copy of this spline.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Clone() : Spline
> ``` 


---  
 #  Create : [spline](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spline.markdown)

 `static`

> Create a new instance of a spline.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Create() : Spline
> ``` 


---  
 #  DebugDraw : Void

> Draw the baked points of the curve with the provided color.
> |Name|Type|Description|
> |---|---|---|
> |color|[real4](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real4.markdown)| |
> ``` lang=cpp, name=Zilch
> function DebugDraw(color : Real4)
> ``` 


---  
 #  ForceRebuild : Void

> Forcibly rebuild the baked points from the control points.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ForceRebuild()
> ``` 


---  
 #  RebuildIfModified : Void

> Rebuild the baked points from the control points if they have changed. Should not need to be manually called unless the user wants to control the timing when the points are baked.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function RebuildIfModified()
> ``` 


---  
 #  SampleDistance : [splinesampledata](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splinesampledata.markdown)

> Samples the curve at a given arc-length distance.
> |Name|Type|Description|
> |---|---|---|
> |distance|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function SampleDistance(distance : Real) : SplineSampleData
> ``` 


---  
 #  SampleNormalized : [splinesampledata](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splinesampledata.markdown)

> Samples the curve with a time in the range of [0, 1].
> |Name|Type|Description|
> |---|---|---|
> |time|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function SampleNormalized(time : Real) : SplineSampleData
> ``` 


---  
 

 