 `Component` `Networking`



(NOTE) Network User. Manages the replication of a single negotiated user on the network.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ AddedByPeer](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/netuser.markdown#addedbypeer-zero-engine)|[ AddedByMyPeer](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/netuser.markdown#addedbymypeer-zero-engin)|[netobject](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/netobject.markdown)| |
|[ FindOwnedNetObjectByName](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/netuser.markdown#findownednetobjectbyname)|[ NetPeerId](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/netuser.markdown#netpeerid-zero-engine-do)| | |
|[ FindOwnedNetObjectByNameInSpace](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/netuser.markdown#findownednetobjectbyname)|[ NetUserId](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/netuser.markdown#netuserid-zero-engine-do)| | |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/netuser.markdown#netuser-void)|[ OwnedNetObjectCount](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/netuser.markdown#ownednetobjectcount-zero)| | |
|[ ReleaseOwnedNetObjects](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/netuser.markdown#releaseownednetobjects-v)|[ OwnedNetObjects](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/netuser.markdown#ownednetobjects-zero-eng)| | |


 #  Properties


---  
 #  AddedByMyPeer : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var AddedByMyPeer : Boolean


---  
 #  NetPeerId : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Adding network peer identifier.
> ``` lang=cpp, name=Zilch
> var NetPeerId : Integer


---  
 #  NetUserId : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Network user identifier.
> ``` lang=cpp, name=Zilch
> var NetUserId : Integer


---  
 #  OwnedNetObjectCount : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Returns the number of net objects owned by this user in all spaces.
> ``` lang=cpp, name=Zilch
> var OwnedNetObjectCount : Integer


---  
 #  OwnedNetObjects : [coghashsetrange](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/coghashsetrange.markdown)

 `read-only`

> Returns all net objects owned by this user in all spaces.
> ``` lang=cpp, name=Zilch
> var OwnedNetObjects : CogHashSetRange


---  
 #  Methods


---  
 #  AddedByPeer : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Returns true if the user was added by the specified peer, else false.
> |Name|Type|Description|
> |---|---|---|
> |netPeerId|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddedByPeer(netPeerId : Integer) : Boolean
> ``` 


---  
 #  FindOwnedNetObjectByName : [cog](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cog.markdown)

> Finds a net object with the given name owned by this user in any space, else nullptr.
> |Name|Type|Description|
> |---|---|---|
> |name|[string](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function FindOwnedNetObjectByName(name : String) : Cog
> ``` 


---  
 #  FindOwnedNetObjectByNameInSpace : [cog](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cog.markdown)

> Finds a net object with the given name owned by this user in the specified space, else nullptr.
> |Name|Type|Description|
> |---|---|---|
> |name|[string](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown)| |
> |space|[space](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/space.markdown)| |
> ``` lang=cpp, name=Zilch
> function FindOwnedNetObjectByNameInSpace(name : String, space : Space) : Cog
> ``` 


---  
 #  NetUser : Void

 `constructor`

> Constructor.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function NetUser()
> ``` 


---  
 #  ReleaseOwnedNetObjects : Void

> [Server/Offline] Releases ownership of all net objects owned by this user in all spaces.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ReleaseOwnedNetObjects()
> ``` 


---  
 

 