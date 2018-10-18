 `Engine`

(NOTE) Object cache is use to store objects at runtime.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ ClearStore](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/objectstore.markdown#clearstore-void)|[ EntryCount](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/objectstore.markdown#entrycount-zero-engine-d)| | |
|[ Erase](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/objectstore.markdown#erase-void)| | | |
|[ GetDirectoryPath](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/objectstore.markdown#getdirectorypath-zero-en)| | | |
|[ GetEntryAt](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/objectstore.markdown#getentryat-zero-engine-d)| | | |
|[ IsEntryStored](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/objectstore.markdown#isentrystored-zero-engin)| | | |
|[ IsStored](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/objectstore.markdown#isstored-zero-engine-doc)| | | |
|[ Restore](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/objectstore.markdown#restore-zero-engine-docu)| | | |
|[ RestoreOrArchetype](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/objectstore.markdown#restoreorarchetype-zero)| | | |
|[ Store](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/objectstore.markdown#store-zero-engine-docume)| | | |


 #  Properties


---  
 #  EntryCount : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> Get number of entries in the ObjectStore.
> ``` lang=cpp, name=Zilch
> var EntryCount : Integer


---  
 #  Methods


---  
 #  ClearStore : Void

> Clear the store.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ClearStore()
> ``` 


---  
 #  Erase : Void

> Attempts to remove an object from the store.
> |Name|Type|Description|
> |---|---|---|
> |name|[string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function Erase(name : String)
> ``` 


---  
 #  GetDirectoryPath : [string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)

> Returns the directory path to the object store.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function GetDirectoryPath() : String
> ``` 


---  
 #  GetEntryAt : [string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)

> Get the ObjectStore entry at the specified index.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetEntryAt(index : Integer) : String
> ``` 


---  
 #  IsEntryStored : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Is there an entry record for the object in the store?
> |Name|Type|Description|
> |---|---|---|
> |name|[string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function IsEntryStored(name : String) : Boolean
> ``` 


---  
 #  IsStored : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> ||[string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function IsStored( : String) : Boolean
> ``` 


---  
 #  Restore : [cog](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/cog.markdown)

> Restore an object to the space.
> |Name|Type|Description|
> |---|---|---|
> |name|[string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |space|[space](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/space.markdown)| |
> ``` lang=cpp, name=Zilch
> function Restore(name : String, space : Space) : Cog
> ``` 


---  
 #  RestoreOrArchetype : [cog](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/cog.markdown)

> Restore an object if it is not stored use the archetype to create it.
> |Name|Type|Description|
> |---|---|---|
> |name|[string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |archetype|[archetype](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/archetype.markdown)| |
> |space|[space](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/space.markdown)| |
> ``` lang=cpp, name=Zilch
> function RestoreOrArchetype(name : String, archetype : Archetype, space : Space) : Cog
> ``` 


---  
 #  Store : [StoreResult](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#storeresult)

> Store an object.
> |Name|Type|Description|
> |---|---|---|
> |name|[string](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |object|[cog](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/cog.markdown)| |
> ``` lang=cpp, name=Zilch
> function Store(name : String, object : Cog) : StoreResult
> ``` 


---  
 
  
  
  
  
  
  
  

 