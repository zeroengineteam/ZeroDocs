 `Event` `Networking`



(NOTE) Dispatched after an outgoing/incoming net channel property change is detected during a particular replication phase.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
| |[ ChannelName](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchannelpropertychange.markdown#channelname-zero-engine)|[event](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/event.markdown)| |
| |[ ComponentName](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchannelpropertychange.markdown#componentname-zero-engin)| | |
| |[ Direction](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchannelpropertychange.markdown#direction-zero-engine-do)| | |
| |[ Object](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchannelpropertychange.markdown#object-zero-engine-docum)| | |
| |[ PropertyName](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchannelpropertychange.markdown#propertyname-zero-engine)| | |
| |[ ReplicationPhase](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchannelpropertychange.markdown#replicationphase-zero-en)| | |
| |[ Timestamp](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchannelpropertychange.markdown#timestamp-zero-engine-do)| | |


 #  Properties


---  
 #  ChannelName : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `read-only`

> The changed net channel.
> ``` lang=cpp, name=Zilch
> var ChannelName : String


---  
 #  ComponentName : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `read-only`

> The component which declared the changed net property.
> ``` lang=cpp, name=Zilch
> var ComponentName : String


---  
 #  Direction : [TransmissionDirection](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#transmissiondirection)

 `read-only`

> The change direction.
> ``` lang=cpp, name=Zilch
> var Direction : TransmissionDirection


---  
 #  Object : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

 `read-only`

> The changed net object.
> ``` lang=cpp, name=Zilch
> var Object : Cog


---  
 #  PropertyName : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `read-only`

> The changed net property.
> ``` lang=cpp, name=Zilch
> var PropertyName : String


---  
 #  ReplicationPhase : [ReplicationPhase](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#replicationphase)

 `read-only`

> The replication phase.
> ``` lang=cpp, name=Zilch
> var ReplicationPhase : ReplicationPhase


---  
 #  Timestamp : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

 `read-only`

> The time this change occurred.
> ``` lang=cpp, name=Zilch
> var Timestamp : Real


---  
 #  Methods


---  
 

 