 `Event` `Networking`



(NOTE) Dispatched after sending a connect response. If denied, their net peer ID is released and link is destroyed immediately after this.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
| |[ OurConnectResponse](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpeersentconnectresponse.markdown#ourconnectresponse-zero)|[event](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/event.markdown)| |
| |[ OurIpAddress](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpeersentconnectresponse.markdown#ouripaddress-zero-engine)| | |
| |[ OurResponseBundle](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpeersentconnectresponse.markdown#ourresponsebundle-zero-e)| | |
| |[ TheirIpAddress](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpeersentconnectresponse.markdown#theiripaddress-zero-engi)| | |
| |[ TheirNetPeerId](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpeersentconnectresponse.markdown#theirnetpeerid-zero-engi)| | |
| |[ TheirPendingUserAddRequestCount](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpeersentconnectresponse.markdown#theirpendinguseraddreque)| | |
| |[ TheirRequestBundle](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpeersentconnectresponse.markdown#theirrequestbundle-zero)| | |


 #  Properties


---  
 #  OurConnectResponse : [ConnectResponse](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#connectresponse)

 `read-only`

> Our connect response.
> ``` lang=cpp, name=Zilch
> var OurConnectResponse : ConnectResponse


---  
 #  OurIpAddress : [ipaddress](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/ipaddress.markdown)

 `read-only`

> Our IP address (as seen from their perspective).
> ``` lang=cpp, name=Zilch
> var OurIpAddress : IpAddress


---  
 #  OurResponseBundle : [eventbundle](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/eventbundle.markdown)

 `read-only`

> Our bundled response event data.
> ``` lang=cpp, name=Zilch
> var OurResponseBundle : EventBundle


---  
 #  TheirIpAddress : [ipaddress](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/ipaddress.markdown)

 `read-only`

> Their IP address (as seen from our perspective).
> ``` lang=cpp, name=Zilch
> var TheirIpAddress : IpAddress


---  
 #  TheirNetPeerId : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Their net peer ID (set only if accepted).
> ``` lang=cpp, name=Zilch
> var TheirNetPeerId : Integer


---  
 #  TheirPendingUserAddRequestCount : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Their pending user add requests following this connect request (within the same frame).
> ``` lang=cpp, name=Zilch
> var TheirPendingUserAddRequestCount : Integer


---  
 #  TheirRequestBundle : [eventbundle](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/eventbundle.markdown)

 `read-only`

> Their bundled request event data.
> ``` lang=cpp, name=Zilch
> var TheirRequestBundle : EventBundle


---  
 #  Methods


---  
 

 