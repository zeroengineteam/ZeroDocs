 `Physics`

(NOTE) Used to specify which collision group events should be sent out for a CollisionFilter. Allows customizing who gets events (in the filter pair) and what event name is sent out.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
| |[ BlockType](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/collisionfilterblock.markdown#blocktype-zero-engine-do)|[safeid32object](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/safeid32object.markdown)|[collisionendblock](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/collisionendblock.markdown)|
| |[ EventOverride](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/collisionfilterblock.markdown#eventoverride-zero-engin)| |[collisionpersistedblock](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/collisionpersistedblock.markdown)|
| |[ SendEventsToA](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/collisionfilterblock.markdown#sendeventstoa-zero-engin)| |[collisionstartblock](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/collisionstartblock.markdown)|
| |[ SendEventsToB](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/collisionfilterblock.markdown#sendeventstob-zero-engin)| |[presolveblock](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/presolveblock.markdown)|
| |[ SendEventsToSpace](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/collisionfilterblock.markdown#sendeventstospace-zero-e)| | |


 #  Properties


---  
 #  BlockType : [CollisionFilterBlockType](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#collisionfilterblocktype)

 `read-only`

> What type of collision filter block is this?
> ``` lang=cpp, name=Zilch
> var BlockType : CollisionFilterBlockType


---  
 #  EventOverride : [string](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown)

> What event name to send out when this block triggers. If left empty the default name will be used (e.g. GroupCollisionStarted).
> ``` lang=cpp, name=Zilch
> var EventOverride : String


---  
 #  SendEventsToA : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Does the first object in the filter get this event type sent to it?
> ``` lang=cpp, name=Zilch
> var SendEventsToA : Boolean


---  
 #  SendEventsToB : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Does the second object in the filter get this event type sent to it?
> ``` lang=cpp, name=Zilch
> var SendEventsToB : Boolean


---  
 #  SendEventsToSpace : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Does the active space of the objects get this event type sent to it?
> ``` lang=cpp, name=Zilch
> var SendEventsToSpace : Boolean


---  
 #  Methods


---  
 

 