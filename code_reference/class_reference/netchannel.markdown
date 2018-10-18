 `Networking`



(NOTE) Network Channel. Manages the replication of a set of properties on the network.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ GetNetProperty](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchannel.markdown#getnetproperty-zero-engi)|[ Authority](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchannel.markdown#authority-zero-engine-do)|[safeid32object](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/safeid32object.markdown)| |
|[ HasNetProperty](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchannel.markdown#hasnetproperty-zero-engi)|[ ChangeFlag](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchannel.markdown#changeflag-zero-engine-d)| | |
|[ ReplicateNow](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchannel.markdown#replicatenow-zero-engine)|[ IsNapping](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchannel.markdown#isnapping-zero-engine-do)| | |
|[ TakeNap](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchannel.markdown#takenap-void)|[ IsScheduled](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchannel.markdown#isscheduled-zero-engine)| | |
|[ WakeUp](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchannel.markdown#wakeup-void)|[ LastChangeTimePassed](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchannel.markdown#lastchangetimepassed-zer)| | |
| |[ LastChangeTimestamp](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchannel.markdown#lastchangetimestamp-zero)| | |
| |[ Name](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchannel.markdown#name-zero-engine-documen)| | |
| |[ NetChannelType](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchannel.markdown#netchanneltype-zero-engi)| | |


 #  Properties


---  
 #  Authority : [Authority](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#authority)

> Controls which peer has the authority to observe and replicate property changes. (Client: Indicates both the client and server are allowed to observe and replicate property changes) (Server: Indicates only the server is allowed to observe and replicate property changes) Only a single client, specified by NetObject::NetUserOwnerPeerId, may possess client authority at any given time. The server is still responsible for relaying contained property changes to other clients, but will not replicate contained property changes back to the authority client. However, the server is also still responsible for other replication commands (such as object creation/destruction), and these WILL be replicated to the authority client.
> ``` lang=cpp, name=Zilch
> var Authority : Authority


---  
 #  ChangeFlag : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Manual change flag (checked upon manual change observation).
> ``` lang=cpp, name=Zilch
> var ChangeFlag : Boolean


---  
 #  IsNapping : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> Returns true if the net channel is currently napping (performing change detection on longer intervals), else false.
> ``` lang=cpp, name=Zilch
> var IsNapping : Boolean


---  
 #  IsScheduled : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> Returns true if this net channel is scheduled for change observation, else false.
> ``` lang=cpp, name=Zilch
> var IsScheduled : Boolean


---  
 #  LastChangeTimePassed : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

 `read-only`

> Elapsed time passed since this net channel was last changed, else 0.
> ``` lang=cpp, name=Zilch
> var LastChangeTimePassed : Real


---  
 #  LastChangeTimestamp : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

 `read-only`

> Timestamp indicating when this net channel was last changed, else 0.
> ``` lang=cpp, name=Zilch
> var LastChangeTimestamp : Real


---  
 #  Name : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `read-only`

> Net channel name.
> ``` lang=cpp, name=Zilch
> var Name : String


---  
 #  NetChannelType : [netchanneltype](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netchanneltype.markdown)

 `read-only`

> Operating net channel type.
> ``` lang=cpp, name=Zilch
> var NetChannelType : NetChannelType


---  
 #  Methods


---  
 #  GetNetProperty : [netproperty](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netproperty.markdown)

> [Client/Server] Returns the specified net property, else nullptr.
> |Name|Type|Description|
> |---|---|---|
> |component|[component](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/component.markdown)| |
> |propertyName|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetNetProperty(component : Component, propertyName : String) : NetProperty
> ``` 


---  
 #  HasNetProperty : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> [Client/Server] Returns true if the net object has the specified net property, else false.
> |Name|Type|Description|
> |---|---|---|
> |component|[component](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/component.markdown)| |
> |propertyName|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function HasNetProperty(component : Component, propertyName : String) : Boolean
> ``` 


---  
 #  ReplicateNow : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Replicates net property changes immediately (only if changes are detected). Will also update nap state as configured. Returns true if changes were replicated, else false.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ReplicateNow() : Boolean
> ``` 


---  
 #  TakeNap : Void

> Forces the net channel to start napping immediately.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function TakeNap()
> ``` 


---  
 #  WakeUp : Void

> Forces the net channel to stop napping immediately.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function WakeUp()
> ``` 


---  
 

 