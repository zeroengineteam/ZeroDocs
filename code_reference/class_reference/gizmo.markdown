 `Component` `Editor`



(NOTE) Registers itself with the GizmoSpace. This allows GizmoSpace to keep track of which Gizmo the mouse is over, as well as send other input events directly to Gizmos.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gizmo.markdown#gizmo-void)|[ Active](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gizmo.markdown#active-zero-engine-docum)|[component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/component.markdown)| |
| |[ EditingObject](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gizmo.markdown#editingobject-zero-engin)| | |
| |[ ForwardEventsToChildren](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gizmo.markdown#forwardeventstochildren)| | |
| |[ MouseOver](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/gizmo.markdown#mouseover-zero-engine-do)| | |


 #  Properties


---  
 #  Active : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> If set to false, it will not receive input events.
> ``` lang=cpp, name=Zilch
> var Active : Boolean


---  
 #  EditingObject : [cog](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/cog.markdown)

 `read-only`

> Needed?
> ``` lang=cpp, name=Zilch
> var EditingObject : Cog


---  
 #  ForwardEventsToChildren : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> You may want to manually forward the input events to specific children.
> ``` lang=cpp, name=Zilch
> var ForwardEventsToChildren : Boolean


---  
 #  MouseOver : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> Whether or not the mouse is currently over the gizmo.
> ``` lang=cpp, name=Zilch
> var MouseOver : Boolean


---  
 #  Methods


---  
 #  Gizmo : Void

 `constructor`

> Constructor.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Gizmo()
> ``` 


---  
 
  
  
  
  
  
  
  

 