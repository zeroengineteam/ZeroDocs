 `Event` `Networking`



(NOTE) Dispatched before a received net event is dispatched.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
| |[ Destination](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/neteventreceived.markdown#destination-zero-engine)|[event](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/event.markdown)| |
| |[ NetEvent](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/neteventreceived.markdown#netevent-zero-engine-doc)| | |
| |[ ReturnAllow](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/neteventreceived.markdown#returnallow-zero-engine)| | |
| |[ TheirNetPeerId](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/neteventreceived.markdown#theirnetpeerid-zero-engi)| | |


 #  Properties


---  
 #  Destination : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

 `read-only`

> Dispatch destination object (null if the net object could not be found locally).
> ``` lang=cpp, name=Zilch
> var Destination : Cog


---  
 #  NetEvent : [event](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/event.markdown)

 `read-only`

> Network event received.
> ``` lang=cpp, name=Zilch
> var NetEvent : Event


---  
 #  ReturnAllow : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Return: Allow the received network event to be dispatched on the destination object?
> ``` lang=cpp, name=Zilch
> var ReturnAllow : Boolean


---  
 #  TheirNetPeerId : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Their net peer ID.
> ``` lang=cpp, name=Zilch
> var TheirNetPeerId : Integer


---  
 #  Methods


---  
 

 