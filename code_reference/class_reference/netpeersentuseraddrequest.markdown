 `Event` `Networking`



(NOTE) Dispatched after sending a net user add request.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
| |[ OurRequestBundle](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/netpeersentuseraddrequest.markdown#ourrequestbundle-zero-en)|[event](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/event.markdown)| |
| |[ TheirIpAddress](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/netpeersentuseraddrequest.markdown#theiripaddress-zero-engi)| | |
| |[ TheirNetPeerId](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/netpeersentuseraddrequest.markdown#theirnetpeerid-zero-engi)| | |


 #  Properties


---  
 #  OurRequestBundle : [eventbundle](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/eventbundle.markdown)

 `read-only`

> Our bundled request event data.
> ``` lang=cpp, name=Zilch
> var OurRequestBundle : EventBundle


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
 

 