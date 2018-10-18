 `Engine`

(NOTE) Control points for the Spline class. Modifying this will cause the spline to be marked as modified to rebuild the baked curve when needed.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Add](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splinecontrolpoints.markdown#add-void)|[ Count](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splinecontrolpoints.markdown#count-zero-engine-docume)|[safeid32object](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/safeid32object.markdown)| |
|[ Clear](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splinecontrolpoints.markdown#clear-void)| | | |
|[ Get](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splinecontrolpoints.markdown#get-zero-engine-document)| | | |
|[ Set](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splinecontrolpoints.markdown#set-void)| | | |


 #  Properties


---  
 #  Count : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> The number of control points contained.
> ``` lang=cpp, name=Zilch
> var Count : Integer


---  
 #  Methods


---  
 #  Add : Void

> Add a new point to the end of the array.
> |Name|Type|Description|
> |---|---|---|
> |controlPoint|[splinecontrolpoint](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splinecontrolpoint.markdown)| |
> ``` lang=cpp, name=Zilch
> function Add(controlPoint : SplineControlPoint)
> ``` 


---  
 #  Clear : Void

> Clear all control points.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Clear()
> ``` 


---  
 #  Get : [splinecontrolpoint](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splinecontrolpoint.markdown)

> Get the control point at the given index.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Get(index : Integer) : SplineControlPoint
> ``` 


---  
 #  Set : Void

> Sets the control point at the given index.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |value|[splinecontrolpoint](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splinecontrolpoint.markdown)| |
> ``` lang=cpp, name=Zilch
> function Set(index : Integer, value : SplineControlPoint)
> ``` 


---  
 

 