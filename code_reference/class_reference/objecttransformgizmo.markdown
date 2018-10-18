 `Component` `Editor`



|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ AddObject](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objecttransformgizmo.markdown#addobject-void)|[ Basis](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objecttransformgizmo.markdown#basis-zero-engine-docume)|[component](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/component.markdown)|[objectrotategizmo](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objectrotategizmo.markdown)|
|[ ClearObjects](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objecttransformgizmo.markdown#clearobjects-void)|[ ObjectCount](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objecttransformgizmo.markdown#objectcount-zero-engine)| |[objectscalegizmo](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objectscalegizmo.markdown)|
|[ GetObjectAtIndex](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objecttransformgizmo.markdown#getobjectatindex-zero-en)|[ Pivot](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objecttransformgizmo.markdown#pivot-zero-engine-docume)| |[objecttranslategizmo](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objecttranslategizmo.markdown)|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objecttransformgizmo.markdown#objecttransformgizmo-voi)| | | |
|[ RemoveObject](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objecttransformgizmo.markdown#removeobject-void)| | | |
|[ SetOperationQueue](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objecttransformgizmo.markdown#setoperationqueue-void)| | | |
|[ ToggleCoordinateMode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/objecttransformgizmo.markdown#togglecoordinatemode-voi)| | | |


 #  Properties


---  
 #  Basis : [GizmoBasis](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#gizmobasis)

> Setters / Getters.
> ``` lang=cpp, name=Zilch
> var Basis : GizmoBasis


---  
 #  ObjectCount : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Object getters.
> ``` lang=cpp, name=Zilch
> var ObjectCount : Integer


---  
 #  Pivot : [GizmoPivot](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#gizmopivot)

> 
> ``` lang=cpp, name=Zilch
> var Pivot : GizmoPivot


---  
 #  Methods


---  
 #  AddObject : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ||[anyhandle](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/anyhandle.markdown)| |
> ||[boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddObject( : AnyHandle,  : Boolean)
> ``` 


---  
 #  ClearObjects : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ClearObjects()
> ``` 


---  
 #  GetObjectAtIndex : [anyhandle](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/anyhandle.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetObjectAtIndex(index : Integer) : AnyHandle
> ``` 


---  
 #  ObjectTransformGizmo : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ObjectTransformGizmo()
> ``` 


---  
 #  RemoveObject : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ||[anyhandle](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/anyhandle.markdown)| |
> ||[boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)| |
> ``` lang=cpp, name=Zilch
> function RemoveObject( : AnyHandle,  : Boolean)
> ``` 


---  
 #  SetOperationQueue : Void

> If set, this Gizmo will add operations for all modifications to cogs.
> |Name|Type|Description|
> |---|---|---|
> |opQueue|[operationqueue](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/operationqueue.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetOperationQueue(opQueue : OperationQueue)
> ``` 


---  
 #  ToggleCoordinateMode : Void

> Toggle between local / world.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ToggleCoordinateMode()
> ``` 


---  
 

 