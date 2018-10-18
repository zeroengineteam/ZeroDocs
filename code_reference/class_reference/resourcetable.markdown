 `Resource` `Engine`



(NOTE) A table of resources (or strings) that can be indexed, searched by name, or sampled randomly. The table can be randomly sampled to return an entry into the table.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ AddOrError](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#addorerror-void)|[ All](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#all-zero-engine-document)|[dataresource](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/dataresource.markdown)| |
|[ AddOrIgnore](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#addorignore-zero-engine)|[ Count](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#count-zero-engine-docume)| | |
|[ AddOrOverwrite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#addoroverwrite-zero-engi)|[ MaxWeight](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#maxweight-zero-engine-do)| | |
|[ Clear](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#clear-void)|[ ResourceType](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#resourcetype-zero-engine)| | |
|[ Contains](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#contains-zero-engine-doc)| | | |
|[ CreateRuntime](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#createruntime-zero-engin)| | | |
|[ ForceRebuild](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#forcerebuild-void)| | | |
|[ Get](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#get-zero-engine-document)| | | |
|[ GetOrDefault](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#getordefault-zero-engine)| | | |
|[ GetOrError](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#getorerror-zero-engine-d)| | | |
|[ GetOrNull](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#getornull-zero-engine-do)| | | |
|[ RemoveAt](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#removeat-void)| | | |
|[ RemoveOrError](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#removeorerror-void)| | | |
|[ RemoveOrIgnore](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#removeorignore-zero-engi)| | | |
|[ RuntimeClone](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#runtimeclone-zero-engine)| | | |
|[ Sample](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#sample-zero-engine-docum)| | | |
|[ SampleIndex](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#sampleindex-zero-engine)| | | |
|[ Set](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown#set-void)| | | |


 #  Properties


---  
 #  All : [resourcetableentryrange](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetableentryrange.markdown)

 `read-only`

> Range to iterate over all entries.
> ``` lang=cpp, name=Zilch
> var All : ResourceTableEntryRange


---  
 #  Count : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> How many items are stored in the table.
> ``` lang=cpp, name=Zilch
> var Count : Integer


---  
 #  MaxWeight : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The maximum probability weight value that can be stored in the table. Setting this will clamp all weight values.
> ``` lang=cpp, name=Zilch
> var MaxWeight : Real


---  
 #  ResourceType : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

> The kind of resource contained in this table. This is either a resource type or "String".
> ``` lang=cpp, name=Zilch
> var ResourceType : String


---  
 #  Methods


---  
 #  AddOrError : Void

> Add the given entry. If another entry with the same name exists then an error is thrown.
> |Name|Type|Description|
> |---|---|---|
> |entry|[resourcetableentry](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetableentry.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddOrError(entry : ResourceTableEntry)
> ``` 


---  
 #  AddOrIgnore : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Add the given entry. If another entry with the same name exists then no operation is performed.
> |Name|Type|Description|
> |---|---|---|
> |entry|[resourcetableentry](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetableentry.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddOrIgnore(entry : ResourceTableEntry) : Boolean
> ``` 


---  
 #  AddOrOverwrite : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Add the given entry. If another entry with the same name exists then it is overwritten.
> |Name|Type|Description|
> |---|---|---|
> |entry|[resourcetableentry](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetableentry.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddOrOverwrite(entry : ResourceTableEntry) : Boolean
> ``` 


---  
 #  Clear : Void

> Clear all items in the table.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Clear()
> ``` 


---  
 #  Contains : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Returns if the given key is contained.
> |Name|Type|Description|
> |---|---|---|
> |key|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function Contains(key : String) : Boolean
> ``` 


---  
 #  CreateRuntime : [resourcetable](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown)

 `static`

> Creates a ResourceTable for run-time modifications.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function CreateRuntime() : ResourceTable
> ``` 


---  
 #  ForceRebuild : Void

> Force rebuild the weighted probability table.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ForceRebuild()
> ``` 


---  
 #  Get : [resourcetableentry](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetableentry.markdown)

> Access an item at the given index.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Get(index : Integer) : ResourceTableEntry
> ``` 


---  
 #  Get : [resourcetableentry](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetableentry.markdown)

> Hash-Set interface. Gets the item with the same name as the entry.
> |Name|Type|Description|
> |---|---|---|
> |entry|[resourcetableentry](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetableentry.markdown)| |
> ``` lang=cpp, name=Zilch
> function Get(entry : ResourceTableEntry) : ResourceTableEntry
> ``` 


---  
 #  Get : [resourcetableentry](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetableentry.markdown)

> Hash-Map interface. Gets via the provided key.
> |Name|Type|Description|
> |---|---|---|
> |key|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function Get(key : String) : ResourceTableEntry
> ``` 


---  
 #  GetOrDefault : [resourcetableentry](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetableentry.markdown)

> Returns the entry associated with the given key. If no entry matches the key then the provided default is returned.
> |Name|Type|Description|
> |---|---|---|
> |key|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |defaultValue|[resourcetableentry](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetableentry.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetOrDefault(key : String, defaultValue : ResourceTableEntry) : ResourceTableEntry
> ``` 


---  
 #  GetOrError : [resourcetableentry](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetableentry.markdown)

> Returns the entry associated with the given key. If no entry matches the key then an exception is thrown.
> |Name|Type|Description|
> |---|---|---|
> |key|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetOrError(key : String) : ResourceTableEntry
> ``` 


---  
 #  GetOrNull : [resourcetableentry](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetableentry.markdown)

> Returns the entry associated with the given key. If no entry matches then null is returned.
> |Name|Type|Description|
> |---|---|---|
> |key|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetOrNull(key : String) : ResourceTableEntry
> ``` 


---  
 #  RemoveAt : Void

> Removes the item at the given index.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function RemoveAt(index : Integer)
> ``` 


---  
 #  RemoveOrError : Void

> Removes the entry associated with the given key. If no entry matches an exception is thrown.
> |Name|Type|Description|
> |---|---|---|
> |key|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function RemoveOrError(key : String)
> ``` 


---  
 #  RemoveOrIgnore : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Removes the entry associated with the given key. If no entry matches then no operation is performed.
> |Name|Type|Description|
> |---|---|---|
> |key|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function RemoveOrIgnore(key : String) : Boolean
> ``` 


---  
 #  RuntimeClone : [resourcetable](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetable.markdown)

> Creates a clone of this table for run-time modifications.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function RuntimeClone() : ResourceTable
> ``` 


---  
 #  Sample : [resourcetableentry](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetableentry.markdown)

> Samples the table to return a random entry. Takes two (different) random floats from [0,1) in order to sample. Returns an empty string if the table is empty.
> |Name|Type|Description|
> |---|---|---|
> |random1|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |random2|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Sample(random1 : Real, random2 : Real) : ResourceTableEntry
> ``` 


---  
 #  SampleIndex : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

> Samples the table to return a random index into the table. Takes two (different) random floats from [0,1) in order to sample.
> |Name|Type|Description|
> |---|---|---|
> |random1|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |random2|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function SampleIndex(random1 : Real, random2 : Real) : Integer
> ``` 


---  
 #  Set : Void

> Access an item at the given index.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |entry|[resourcetableentry](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetableentry.markdown)| |
> ``` lang=cpp, name=Zilch
> function Set(index : Integer, entry : ResourceTableEntry)
> ``` 


---  
 #  Set : Void

> Hash-Set interface. Sets the item with the same name as the entry.
> |Name|Type|Description|
> |---|---|---|
> |entry|[resourcetableentry](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetableentry.markdown)| |
> ``` lang=cpp, name=Zilch
> function Set(entry : ResourceTableEntry)
> ``` 


---  
 #  Set : Void

> Hash-Map interface. Sets via the provided key.
> |Name|Type|Description|
> |---|---|---|
> |key|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |entry|[resourcetableentry](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/resourcetableentry.markdown)| |
> ``` lang=cpp, name=Zilch
> function Set(key : String, entry : ResourceTableEntry)
> ``` 


---  
 

 