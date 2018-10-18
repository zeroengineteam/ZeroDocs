 `Component` `Physics`



(NOTE) A stick joint is used to simulate a rope or a stick. This joint forces a constant distance between the anchor points on the objects. If there is no limit, this behaves as a stick. If there is a limit, then this behaves as a rope. Motors and springs are also applied to the axis of the rope. Add on definitions: Limit: A limit will provide a min/max distance that the anchors can be between. Motor: A motor will push/pull the objects in the direction of the rope. The motor will not have any effect unless a limit or spring is present. Spring: A spring will make the rope behave spring-like at its boundaries.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ SetWorldPoints](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/stickjoint.markdown#setworldpoints-void)|[ Length](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/stickjoint.markdown#length-zero-engine-docum)|[joint](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/joint.markdown)| |
|[ Constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/stickjoint.markdown#stickjoint-void)|[ LocalPointA](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/stickjoint.markdown#localpointa-zero-engine)| | |
| |[ LocalPointB](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/stickjoint.markdown#localpointb-zero-engine)| | |
| |[ WorldPointA](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/stickjoint.markdown#worldpointa-zero-engine)| | |
| |[ WorldPointB](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/stickjoint.markdown#worldpointb-zero-engine)| | |


 #  Properties


---  
 #  Length : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The desired length between the anchor points of object A and B.
> ``` lang=cpp, name=Zilch
> var Length : Real


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
 #  StickJoint : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function StickJoint()
> ``` 


---  
 
  
  
  
  
  
  
  

 