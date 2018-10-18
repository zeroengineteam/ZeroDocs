 `Networking`

(NOTE) Describes a network host.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
| |[ BasicHostInfo](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/nethost.markdown#basichostinfo-zero-engin)|[safeid32](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/safeid32.markdown)| |
| |[ ExtraHostInfo](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/nethost.markdown#extrahostinfo-zero-engin)| | |
| |[ IpAddress](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/nethost.markdown#ipaddress-zero-engine-do)| | |
| |[ Latency](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/nethost.markdown#latency-zero-engine-docu)| | |
| |[ Network](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/nethost.markdown#network-zero-engine-docu)| | |
| |[ RoundTripTime](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/nethost.markdown#roundtriptime-zero-engin)| | |


 #  Properties


---  
 #  BasicHostInfo : [eventbundle](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/eventbundle.markdown)

 `read-only`

> Basic host info (limited to 480 bytes).
> ``` lang=cpp, name=Zilch
> var BasicHostInfo : EventBundle


---  
 #  ExtraHostInfo : [eventbundle](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/eventbundle.markdown)

 `read-only`

> Extra host info.
> ``` lang=cpp, name=Zilch
> var ExtraHostInfo : EventBundle


---  
 #  IpAddress : [ipaddress](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ipaddress.markdown)

 `read-only`

> Host's IP address.
> ``` lang=cpp, name=Zilch
> var IpAddress : IpAddress


---  
 #  Latency : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Returns the estimated latency ((RTT/2)) in milliseconds from our peer to this host.
> ``` lang=cpp, name=Zilch
> var Latency : Integer


---  
 #  Network : [Network](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#network)

 `read-only`

> Host's network residence.
> ``` lang=cpp, name=Zilch
> var Network : Network


---  
 #  RoundTripTime : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Returns the round-trip time (RTT) in milliseconds from our peer to this host.
> ``` lang=cpp, name=Zilch
> var RoundTripTime : Integer


---  
 #  Methods


---  
 

 