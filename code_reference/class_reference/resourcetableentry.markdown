 `Engine`

(NOTE) An entry from a resource table. The resource type of this entry must match the resource type of the table to add/set. If the value is set via string then the type will be implicitly set to string, otherwise the type must be set via the Resource property.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Clone](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/resourcetableentry.markdown#clone-zero-engine-docume)|[ Name](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/resourcetableentry.markdown#name-zero-engine-documen)| | |
|[ Constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/resourcetableentry.markdown#resourcetableentry-void)|[ Resource](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/resourcetableentry.markdown#resource-resource)| | |
| |[ ResourceType](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/resourcetableentry.markdown#resourcetype-zero-engine)| | |
| |[ Value](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/resourcetableentry.markdown#value-zero-engine-docume)| | |
| |[ Weight](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/resourcetableentry.markdown#weight-zero-engine-docum)| | |


 #  Properties


---  
 #  Name : [string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Name : String


---  
 #  Resource : Resource

> The resource value of this entry. Returns null if the underlying type is not a resource. Changes this entry's type to the given resource's type on Set.
> ``` lang=cpp, name=Zilch
> var Resource : Resource


---  
 #  ResourceType : [string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)

> 
> ``` lang=cpp, name=Zilch
> var ResourceType : String


---  
 #  Value : [string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)

> The string value of this entry. Changes this entry's type to String on Set.
> ``` lang=cpp, name=Zilch
> var Value : String


---  
 #  Weight : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The weight value used to determine how likely this item is to be sampled. Note: Weights must be positive. Negative weights will be clamped to 0.
> ``` lang=cpp, name=Zilch
> var Weight : Real


---  
 #  Methods


---  
 #  Clone : [resourcetableentry](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/resourcetableentry.markdown)

> Creates a new entry with the same values.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Clone() : ResourceTableEntry
> ``` 


---  
 #  ResourceTableEntry : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ResourceTableEntry()
> ``` 


---  
 #  ResourceTableEntry : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ||[resourcetableentry](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/resourcetableentry.markdown)| |
> ``` lang=cpp, name=Zilch
> function ResourceTableEntry( : ResourceTableEntry)
> ``` 


---  
 
  
  
  
  
  
  
  

 