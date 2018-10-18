 `Event` `Networking`



(NOTE) Dispatched after sending or receiving a disconnect notice. Their net peer ID is released and link is destroyed immediately after this.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
| |[ Direction](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/netlinkdisconnected.markdown#direction-zero-engine-do)|[event](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/event.markdown)| |
| |[ DisconnectReason](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/netlinkdisconnected.markdown#disconnectreason-zero-en)| | |
| |[ RequestBundle](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/netlinkdisconnected.markdown#requestbundle-zero-engin)| | |
| |[ TheirIpAddress](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/netlinkdisconnected.markdown#theiripaddress-zero-engi)| | |
| |[ TheirNetPeerId](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/netlinkdisconnected.markdown#theirnetpeerid-zero-engi)| | |


 #  Properties


---  
 #  Direction : [TransmissionDirection](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#transmissiondirection)

 `read-only`

> Transmission direction.
> ``` lang=cpp, name=Zilch
> var Direction : TransmissionDirection


---  
 #  DisconnectReason : [DisconnectReason](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#disconnectreason)

 `read-only`

> Disconnect reason.
> ``` lang=cpp, name=Zilch
> var DisconnectReason : DisconnectReason


---  
 #  RequestBundle : [eventbundle](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/eventbundle.markdown)

 `read-only`

> Bundled request event data.
> ``` lang=cpp, name=Zilch
> var RequestBundle : EventBundle


---  
 #  TheirIpAddress : [ipaddress](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ipaddress.markdown)

 `read-only`

> Their IP address (as seen from our perspective).
> ``` lang=cpp, name=Zilch
> var TheirIpAddress : IpAddress


---  
 #  TheirNetPeerId : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Their net peer ID.
> ``` lang=cpp, name=Zilch
> var TheirNetPeerId : Integer


---  
 #  Methods


---  
 

 