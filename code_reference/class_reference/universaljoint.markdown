 `Component` `Physics`



(NOTE) A universal joint locks positional movement of two points together as well as locking rotation about one axis. This means it is a joint that constrains four axes and leaves two free rotational axes. This joint is most useful to model something like a arm or leg that has a large range of rotational movement.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ SetWorldPoints](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/universaljoint.markdown#setworldpoints-void)|[ LocalAxis0OfBodyA](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/universaljoint.markdown#localaxis0ofbodya-zero-e)|[joint](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/joint.markdown)| |
|[ Constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/universaljoint.markdown#universaljoint-void)|[ LocalAxis0OfBodyB](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/universaljoint.markdown#localaxis0ofbodyb-zero-e)| | |
| |[ LocalAxis1OfBodyA](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/universaljoint.markdown#localaxis1ofbodya-zero-e)| | |
| |[ LocalAxis1OfBodyB](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/universaljoint.markdown#localaxis1ofbodyb-zero-e)| | |
| |[ LocalPointA](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/universaljoint.markdown#localpointa-zero-engine)| | |
| |[ LocalPointB](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/universaljoint.markdown#localpointb-zero-engine)| | |
| |[ WorldPointA](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/universaljoint.markdown#worldpointa-zero-engine)| | |
| |[ WorldPointB](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/universaljoint.markdown#worldpointb-zero-engine)| | |


 #  Properties


---  
 #  LocalAxis0OfBodyA : [real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)

> One of the two axes in local space of object A that the objects are allowed to rotate about.
> ``` lang=cpp, name=Zilch
> var LocalAxis0OfBodyA : Real3


---  
 #  LocalAxis0OfBodyB : [real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)

> One of the two axes in local space of object B that the objects are allowed to rotate about.
> ``` lang=cpp, name=Zilch
> var LocalAxis0OfBodyB : Real3


---  
 #  LocalAxis1OfBodyA : [real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)

> One of the two axes in local space of object A that the objects are allowed to rotate about.
> ``` lang=cpp, name=Zilch
> var LocalAxis1OfBodyA : Real3


---  
 #  LocalAxis1OfBodyB : [real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)

> One of the two axes in local space of object B that the objects are allowed to rotate about.
> ``` lang=cpp, name=Zilch
> var LocalAxis1OfBodyB : Real3


---  
 #  LocalPointA : [real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)

> The local point of the anchor on object A . 
> ``` lang=cpp, name=Zilch
> var LocalPointA : Real3


---  
 #  LocalPointB : [real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)

> The local point of the anchor on object B . 
> ``` lang=cpp, name=Zilch
> var LocalPointB : Real3


---  
 #  WorldPointA : [real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)

> The position of the anchor on object A given a position in world space 
> ``` lang=cpp, name=Zilch
> var WorldPointA : Real3


---  
 #  WorldPointB : [real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)

> The position of the anchor on object B given a position in world space 
> ``` lang=cpp, name=Zilch
> var WorldPointB : Real3


---  
 #  Methods


---  
 #  SetWorldPoints : Void

> Sets the position of the anchor on object A and B given a position in world space 
> |Name|Type|Description|
> |---|---|---|
> |point|[real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetWorldPoints(point : Real3)
> ``` 


---  
 #  UniversalJoint : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function UniversalJoint()
> ``` 


---  
 
  
  
  
  
  
  
  

 