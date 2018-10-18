 `Event` `Networking`



(NOTE) Dispatched after sending a connect request.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
| |[ OurPendingUserAddRequestCount](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netpeersentconnectrequest.markdown#ourpendinguseraddrequest)|[event](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/event.markdown)| |
| |[ OurRequestBundle](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netpeersentconnectrequest.markdown#ourrequestbundle-zero-en)| | |
| |[ TheirIpAddress](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/netpeersentconnectrequest.markdown#theiripaddress-zero-engi)| | |


 #  Properties


---  
 #  OurPendingUserAddRequestCount : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Our pending user add requests following this connect request (within the same frame).
> ``` lang=cpp, name=Zilch
> var OurPendingUserAddRequestCount : Integer


---  
 #  OurRequestBundle : [eventbundle](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/eventbundle.markdown)

 `read-only`

> Our bundled request event data.
> ``` lang=cpp, name=Zilch
> var OurRequestBundle : EventBundle


---  
 #  TheirIpAddress : [ipaddress](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/ipaddress.markdown)

 `read-only`

> Their IP address (as seen from our perspective).
> ``` lang=cpp, name=Zilch
> var TheirIpAddress : IpAddress


---  
 #  Methods


---  
 
  
  
  
  
  
  
  

 