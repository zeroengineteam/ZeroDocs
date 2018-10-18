 `Physics`

(NOTE) A filter for storing the relationship between a pair of groups. Stores flags for the kind of filter this is, as well as what events to send out and to whom.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collisionfilter.markdown#collisionfilter-void)|[ CollisionFlag](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collisionfilter.markdown#collisionflag-zero-engin)|[safeid32eventobject](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/safeid32eventobject.markdown)| |
| |[ CollisionGroupA](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collisionfilter.markdown#collisiongroupa-zero-eng)| | |
| |[ CollisionGroupB](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collisionfilter.markdown#collisiongroupb-zero-eng)| | |


 #  Properties


---  
 #  CollisionFlag : [CollisionFilterCollisionFlags](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#collisionfiltercollisionflags)

> The collision state between the two types. Controls whether the types skip detection, skip resolution, or resolve as normal.
> ``` lang=cpp, name=Zilch
> var CollisionFlag : CollisionFilterCollisionFlags


---  
 #  CollisionGroupA : [collisiongroup](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collisiongroup.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var CollisionGroupA : CollisionGroup


---  
 #  CollisionGroupB : [collisiongroup](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collisiongroup.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var CollisionGroupB : CollisionGroup


---  
 #  Methods


---  
 #  CollisionFilter : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function CollisionFilter()
> ``` 


---  
 

 