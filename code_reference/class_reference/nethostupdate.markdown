 `Event` `Networking`



(NOTE) Dispatched when a host discovery operation update occurs.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
| |[ Host](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/nethostupdate.markdown#host-zero-engine-documen)|[event](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/event.markdown)| |
| |[ Network](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/nethostupdate.markdown#network-zero-engine-docu)| | |
| |[ RefreshResult](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/nethostupdate.markdown#refreshresult-zero-engin)| | |
| |[ ResponseTime](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/nethostupdate.markdown#responsetime-zero-engine)| | |


 #  Properties


---  
 #  Host : [nethost](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/nethost.markdown)

 `read-only`

> Host discovered or refreshed (will contain the first host updated if this is a list update).
> ``` lang=cpp, name=Zilch
> var Host : NetHost


---  
 #  Network : [Network](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#network)

 `read-only`

> Operation target network.
> ``` lang=cpp, name=Zilch
> var Network : Network


---  
 #  RefreshResult : [NetRefreshResult](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#netrefreshresult)

 `read-only`

> Whether or not the operation completed successfully.
> ``` lang=cpp, name=Zilch
> var RefreshResult : NetRefreshResult


---  
 #  ResponseTime : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

 `read-only`

> Operation response time (from request to completion).
> ``` lang=cpp, name=Zilch
> var ResponseTime : Real


---  
 #  Methods


---  
 

 