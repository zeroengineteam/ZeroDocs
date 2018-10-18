 `Networking`



(NOTE) Network Channel Type. Configures the replication of a set of properties on the network.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ ResetConfig](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#resetconfig-void)|[ AcceptIncomingChanges](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#acceptincomingchanges-ze)|[safeid32object](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/safeid32object.markdown)| |
|[ SetConfig](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#setconfig-void)|[ AccurateTimestampOnChange](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#accuratetimestamponchang)| | |
| |[ AllowNapping](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#allownapping-zero-engine)| | |
| |[ AllowRelay](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#allowrelay-zero-engine-d)| | |
| |[ AuthorityDefault](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#authoritydefault-zero-en)| | |
| |[ AuthorityMode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#authoritymode-zero-engin)| | |
| |[ AwakeDetectionInterval](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#awakedetectioninterval-z)| | |
| |[ AwakeDuration](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#awakeduration-zero-engin)| | |
| |[ DetectionMode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#detectionmode-zero-engin)| | |
| |[ DetectOutgoingChanges](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#detectoutgoingchanges-ze)| | |
| |[ EventOnIncomingPropertyChange](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#eventonincomingpropertyc)| | |
| |[ EventOnOutgoingPropertyChange](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#eventonoutgoingpropertyc)| | |
| |[ Name](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#name-zero-engine-documen)| | |
| |[ NapDetectionInterval](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#napdetectioninterval-zer)| | |
| |[ ReliabilityMode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#reliabilitymode-zero-eng)| | |
| |[ ReplicateOnOffline](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#replicateonoffline-zero)| | |
| |[ ReplicateOnOnline](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#replicateononline-zero-e)| | |
| |[ SerializationMode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#serializationmode-zero-e)| | |
| |[ TransferMode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchanneltype.markdown#transfermode-zero-engine)| | |


 #  Properties


---  
 #  AcceptIncomingChanges : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Controls whether or not net channels should accept incoming changes.
> ``` lang=cpp, name=Zilch
> var AcceptIncomingChanges : Boolean


---  
 #  AccurateTimestampOnChange : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Controls whether or not the net channel will serialize an accurate timestamp value when changed, or will instead accept an estimated timestamp value. (This setting may be overridden for net channels belonging to a specific net object by enabling the corresponding net object setting)
> ``` lang=cpp, name=Zilch
> var AccurateTimestampOnChange : Boolean


---  
 #  AllowNapping : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Controls whether or not net channels may nap (perform change detection on longer intervals) if they haven't changed in a while.
> ``` lang=cpp, name=Zilch
> var AllowNapping : Boolean


---  
 #  AllowRelay : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Controls whether or not net channels will have their changes immediately broadcast to all relevant, incidental peers (if any) once received. (Enabling this allows a server to automatically relay client authoritative changes to other clients, otherwise this must be done manually using NetChannel::ReplicateNow)
> ``` lang=cpp, name=Zilch
> var AllowRelay : Boolean


---  
 #  AuthorityDefault : [Authority](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#authority)

> Controls which peer has the authority to observe and replicate property changes on each net channel by default. (Client: Indicates both the client and server are allowed to observe and replicate property changes) (Server: Indicates only the server is allowed to observe and replicate property changes) Only a single client, specified by NetObject::NetUserOwnerPeerId, may possess client authority at any given time. The server is still responsible for relaying contained property changes to other clients, but will not replicate contained property changes back to the authority client. However, the server is also still responsible for other replication commands (such as object creation/destruction), and these WILL be replicated to the authority client.
> ``` lang=cpp, name=Zilch
> var AuthorityDefault : Authority


---  
 #  AuthorityMode : [AuthorityMode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#authoritymode)

> Controls when net channels can modify their change authority. (Dynamic: Authority may be modified at any time, even after a net object is brought online) (Fixed: Authority may be modified only before a net object is brought online) (Cannot be modified at game runtime)
> ``` lang=cpp, name=Zilch
> var AuthorityMode : AuthorityMode


---  
 #  AwakeDetectionInterval : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

> Controls the frame interval in which awake net channels are observed for changes. (Cannot be modified at game runtime)
> ``` lang=cpp, name=Zilch
> var AwakeDetectionInterval : Integer


---  
 #  AwakeDuration : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

> Controls the frame duration following the last detected change in which net channels are considered actively changing and will be kept awake.
> ``` lang=cpp, name=Zilch
> var AwakeDuration : Integer


---  
 #  DetectionMode : [DetectionMode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#detectionmode)

> Controls how net channel changes are detected. (Assume: Assumes something has changed) (Manual: Detects changes manually using change flags) (Automatic: Detects changes automatically using comparisons) (Manumatic: Detects changes manually using change flags and automatically using comparisons)
> ``` lang=cpp, name=Zilch
> var DetectionMode : DetectionMode


---  
 #  DetectOutgoingChanges : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Controls whether or not net channels should detect outgoing changes.
> ``` lang=cpp, name=Zilch
> var DetectOutgoingChanges : Boolean


---  
 #  EventOnIncomingPropertyChange : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Controls whether or not net channels should dispatch NetChannelIncomingPropertyChange when an incoming net property change is accepted.
> ``` lang=cpp, name=Zilch
> var EventOnIncomingPropertyChange : Boolean


---  
 #  EventOnOutgoingPropertyChange : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Controls whether or not net channels should dispatch NetChannelOutgoingPropertyChange when an outgoing net property change is detected.
> ``` lang=cpp, name=Zilch
> var EventOnOutgoingPropertyChange : Boolean


---  
 #  Name : [string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)

 `read-only`

> Net channel type name.
> ``` lang=cpp, name=Zilch
> var Name : String


---  
 #  NapDetectionInterval : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

> Controls the frame interval in which napping net channels are observed for changes. (Cannot be modified at game runtime)
> ``` lang=cpp, name=Zilch
> var NapDetectionInterval : Integer


---  
 #  ReliabilityMode : [ReliabilityMode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#reliabilitymode)

> Controls whether or not net channel changes will be retransmitted should they get lost over the network. (Unreliable: Lost changes are not retransmitted) (Reliable: Lost changes are retransmitted)
> ``` lang=cpp, name=Zilch
> var ReliabilityMode : ReliabilityMode


---  
 #  ReplicateOnOffline : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Controls whether or not the net channel will be replicated when the net object goes offline. If enabled, all net channel property values are guaranteed to be set immediately before the NetObjectOffline event. (Cannot be modified at game runtime)
> ``` lang=cpp, name=Zilch
> var ReplicateOnOffline : Boolean


---  
 #  ReplicateOnOnline : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Controls whether or not the net channel will be replicated when the net object comes online. If enabled, all net channel property values are guaranteed to be set immediately before the NetObjectOnline event. (Cannot be modified at game runtime)
> ``` lang=cpp, name=Zilch
> var ReplicateOnOnline : Boolean


---  
 #  SerializationMode : [SerializationMode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#serializationmode)

> Controls how net channels are serialized. (All: Serialize all net properties) (Changed: Serialize only net properties that have changed, using bit flags in between) (Cannot be modified at game runtime)
> ``` lang=cpp, name=Zilch
> var SerializationMode : SerializationMode


---  
 #  TransferMode : [TransferMode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#transfermode)

> Controls how net channel changes are to be ordered and released once received. (Immediate: Changes are released immediately once received, including late changes) (Sequenced: Changes are released immediately once received, discarding late changes) (Ordered: Changes are released immediately once preceding late changes have been received; forces all changes to be sent reliably) (Cannot be modified at game runtime)
> ``` lang=cpp, name=Zilch
> var TransferMode : TransferMode


---  
 #  Methods


---  
 #  ResetConfig : Void

> Resets all configuration settings.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ResetConfig()
> ``` 


---  
 #  SetConfig : Void

> Sets all configuration settings according to the specified NetChannelConfig resource.
> |Name|Type|Description|
> |---|---|---|
> |netChannelConfig|[netchannelconfig](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netchannelconfig.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetConfig(netChannelConfig : NetChannelConfig)
> ``` 


---  
 
  
  
  
  
  
  
  

 