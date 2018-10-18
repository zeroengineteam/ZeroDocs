 `Event` `Networking`



(NOTE) Dispatched after sending a net user add response.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
| |[ OurAddResponse](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpeersentuseraddresponse.markdown#ouraddresponse-zero-engi)|[event](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/event.markdown)| |
| |[ OurResponseBundle](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpeersentuseraddresponse.markdown#ourresponsebundle-zero-e)| | |
| |[ TheirIpAddress](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpeersentuseraddresponse.markdown#theiripaddress-zero-engi)| | |
| |[ TheirNetPeerId](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpeersentuseraddresponse.markdown#theirnetpeerid-zero-engi)| | |
| |[ TheirNetUser](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpeersentuseraddresponse.markdown#theirnetuser-zero-engine)| | |
| |[ TheirNetUserId](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpeersentuseraddresponse.markdown#theirnetuserid-zero-engi)| | |
| |[ TheirRequestBundle](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpeersentuseraddresponse.markdown#theirrequestbundle-zero)| | |


 #  Properties


---  
 #  OurAddResponse : [NetUserAddResponse](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#netuseraddresponse)

 `read-only`

> Our add response.
> ``` lang=cpp, name=Zilch
> var OurAddResponse : NetUserAddResponse


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

> Their net peer ID.
> ``` lang=cpp, name=Zilch
> var TheirNetPeerId : Integer


---  
 #  TheirNetUser : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

 `read-only`

> Their net user object about to be added (set only if accepted).
> ``` lang=cpp, name=Zilch
> var TheirNetUser : Cog


---  
 #  TheirNetUserId : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Their net user ID (set only if accepted).
> ``` lang=cpp, name=Zilch
> var TheirNetUserId : Integer


---  
 #  TheirRequestBundle : [eventbundle](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/eventbundle.markdown)

 `read-only`

> Their bundled request event data.
> ``` lang=cpp, name=Zilch
> var TheirRequestBundle : EventBundle


---  
 #  Methods


---  
 

 