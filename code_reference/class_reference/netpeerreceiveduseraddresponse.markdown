 `Event` `Networking`



(NOTE) Dispatched after receiving a net user add response.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
| |[ OurNetUserId](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpeerreceiveduseraddresponse.markdown#ournetuserid-zero-engine)|[event](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/event.markdown)| |
| |[ OurRequestBundle](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpeerreceiveduseraddresponse.markdown#ourrequestbundle-zero-en)| | |
| |[ TheirAddResponse](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpeerreceiveduseraddresponse.markdown#theiraddresponse-zero-en)| | |
| |[ TheirIpAddress](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpeerreceiveduseraddresponse.markdown#theiripaddress-zero-engi)| | |
| |[ TheirNetPeerId](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpeerreceiveduseraddresponse.markdown#theirnetpeerid-zero-engi)| | |
| |[ TheirResponseBundle](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpeerreceiveduseraddresponse.markdown#theirresponsebundle-zero)| | |


 #  Properties


---  
 #  OurNetUserId : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Our net user ID (set only if accepted).
> ``` lang=cpp, name=Zilch
> var OurNetUserId : Integer


---  
 #  OurRequestBundle : [eventbundle](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/eventbundle.markdown)

 `read-only`

> Our bundled request event data.
> ``` lang=cpp, name=Zilch
> var OurRequestBundle : EventBundle


---  
 #  TheirAddResponse : [NetUserAddResponse](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#netuseraddresponse)

 `read-only`

> Their add response.
> ``` lang=cpp, name=Zilch
> var TheirAddResponse : NetUserAddResponse


---  
 #  TheirIpAddress : [ipaddress](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/ipaddress.markdown)

 `read-only`

> Their IP address (as seen from our perspective).
> ``` lang=cpp, name=Zilch
> var TheirIpAddress : IpAddress


---  
 #  TheirNetPeerId : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Their net peer ID.
> ``` lang=cpp, name=Zilch
> var TheirNetPeerId : Integer


---  
 #  TheirResponseBundle : [eventbundle](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/eventbundle.markdown)

 `read-only`

> Their bundled response event data.
> ``` lang=cpp, name=Zilch
> var TheirResponseBundle : EventBundle


---  
 #  Methods


---  
 

 