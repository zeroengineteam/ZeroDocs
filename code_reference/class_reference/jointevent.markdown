 `Event` `Physics`



(NOTE) Sent out when a joint reaches some condition. Currently sent out when a limit is reached or an impulse's limit is exceeded.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
| |[ Joint](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/jointevent.markdown#joint-zero-engine-docume)|[event](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/event.markdown)| |
| |[ JointCog](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/jointevent.markdown#jointcog-zero-engine-doc)| | |
| |[ ObjectA](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/jointevent.markdown#objecta-zero-engine-docu)| | |
| |[ ObjectB](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/jointevent.markdown#objectb-zero-engine-docu)| | |


 #  Properties


---  
 #  Joint : [joint](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/joint.markdown)

 `read-only`

> The Joint that triggered the event.
> ``` lang=cpp, name=Zilch
> var Joint : Joint


---  
 #  JointCog : [cog](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cog.markdown)

 `read-only`

> The Cog of the Joint that signaled the event.
> ``` lang=cpp, name=Zilch
> var JointCog : Cog


---  
 #  ObjectA : [cog](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cog.markdown)

 `read-only`

> ObjectA on the Joint.
> ``` lang=cpp, name=Zilch
> var ObjectA : Cog


---  
 #  ObjectB : [cog](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cog.markdown)

 `read-only`

> ObjectB on the Joint.
> ``` lang=cpp, name=Zilch
> var ObjectB : Cog


---  
 #  Methods


---  
 

 