 `Networking`



(NOTE) Network Property Type. Configures the replication of a single property on the network.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ ResetConfig](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpropertytype.markdown#resetconfig-void)|[ Name](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpropertytype.markdown#name-zero-engine-documen)|[safeid32object](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/safeid32object.markdown)| |
|[ SetConfig](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpropertytype.markdown#setconfig-void)| | | |


 #  Properties


---  
 #  Name : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `read-only`

> Net property type name.
> ``` lang=cpp, name=Zilch
> var Name : String


---  
 #  Methods


---  
 #  ResetConfig : Void

> Resets all configuration settings. (Cannot be modified at game runtime)
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ResetConfig()
> ``` 


---  
 #  SetConfig : Void

> Sets all configuration settings according to the specified NetPropertyConfig resource. (Cannot be modified at game runtime)
> |Name|Type|Description|
> |---|---|---|
> |netPropertyConfig|[netpropertyconfig](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/netpropertyconfig.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetConfig(netPropertyConfig : NetPropertyConfig)
> ``` 


---  
 

 