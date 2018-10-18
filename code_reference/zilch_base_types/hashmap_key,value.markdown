 `Core`(NOTE) Hash Map is an Associative Hashed Container.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[[zero_engine_documentation/code_reference/zilch_base_types/hashmap_key,value /#add-void | Add]]|[[zero_engine_documentation/code_reference/zilch_base_types/hashmap_key,value /#all-zero-engine-document | All]]|HashedContainer<Pair<KeyType,DataType>,PairHashAdapter<Hasher,KeyType,DataType>,Allocator>| |
|[[zero_engine_documentation/code_reference/zilch_base_types/hashmap_key,value /#clear-void | Clear]]|[[zero_engine_documentation/code_reference/zilch_base_types/hashmap_key,value /#count-zero-engine-docume | Count]]| | |
|[[zero_engine_documentation/code_reference/zilch_base_types/hashmap_key,value /#contains-zero-engine-doc | Contains]]|[[zero_engine_documentation/code_reference/zilch_base_types/hashmap_key,value /#keys-zero-engine-documen | Keys]]| | |
|[[zero_engine_documentation/code_reference/zilch_base_types/hashmap_key,value /#get-zero-engine-document | Get]]|[[zero_engine_documentation/code_reference/zilch_base_types/hashmap_key,value /#values-zero-engine-docum | Values]]| | |
|[[zero_engine_documentation/code_reference/zilch_base_types/hashmap_key,value /#getordefault-zero-engine | GetOrDefault]]| | | |
|[[zero_engine_documentation/code_reference/zilch_base_types/hashmap_key,value /#getorerror-zero-engine-d | GetOrError]]| | | |
|[[zero_engine_documentation/code_reference/zilch_base_types/hashmap_key,value /#hashmap-key,value-void | Constructor]]| | | |
|[[zero_engine_documentation/code_reference/zilch_base_types/hashmap_key,value /#removeorerror-void | RemoveOrError]]| | | |
|[[zero_engine_documentation/code_reference/zilch_base_types/hashmap_key,value /#removeorignore-zero-engi | RemoveOrIgnore]]| | | |
|[[zero_engine_documentation/code_reference/zilch_base_types/hashmap_key,value /#set-zero-engine-document | Set]]| | | |
|[[zero_engine_documentation/code_reference/zilch_base_types/hashmap_key,value /#setorerror-void | SetOrError]]| | | |
|[[zero_engine_documentation/code_reference/zilch_base_types/hashmap_key,value /#setorignore-zero-engine | SetOrIgnore]]| | | |
|[[zero_engine_documentation/code_reference/zilch_base_types/hashmap_key,value /#setoroverwrite-zero-engi | SetOrOverwrite]]| | | |


 #  Properties


---  
 #  All : HashMapRange[Key,Value]

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var All : HashMapRange[Key,Value]


---  
 #  Count : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var Count : Integer


---  
 #  Keys : HashMapKeyRange[Key]

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var Keys : HashMapKeyRange[Key]


---  
 #  Values : HashMap[Value]

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var Values : HashMap[Value]


---  
 #  Methods


---  
 #  Add : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ||Key| |
> ||Value| |
> ``` lang=cpp, name=Zilch
> function Add( : Key,  : Value)
> ``` 


---  
 #  Clear : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Clear()
> ``` 


---  
 #  Contains : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> ||Key| |
> ``` lang=cpp, name=Zilch
> function Contains( : Key) : Boolean
> ``` 


---  
 #  Get : Value

> 
> |Name|Type|Description|
> |---|---|---|
> ||Key| |
> ``` lang=cpp, name=Zilch
> function Get( : Key) : Value
> ``` 


---  
 #  GetOrDefault : Value

> 
> |Name|Type|Description|
> |---|---|---|
> ||Key| |
> ``` lang=cpp, name=Zilch
> function GetOrDefault( : Key) : Value
> ``` 


---  
 #  GetOrDefault : Value

> 
> |Name|Type|Description|
> |---|---|---|
> ||Key| |
> ||Value| |
> ``` lang=cpp, name=Zilch
> function GetOrDefault( : Key,  : Value) : Value
> ``` 


---  
 #  GetOrError : Value

> 
> |Name|Type|Description|
> |---|---|---|
> ||Key| |
> ``` lang=cpp, name=Zilch
> function GetOrError( : Key) : Value
> ``` 


---  
 #  HashMap[Key,Value] : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function HashMap[Key,Value]()
> ``` 


---  
 #  RemoveOrError : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ||Key| |
> ``` lang=cpp, name=Zilch
> function RemoveOrError( : Key)
> ``` 


---  
 #  RemoveOrIgnore : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> ||Key| |
> ``` lang=cpp, name=Zilch
> function RemoveOrIgnore( : Key) : Boolean
> ``` 


---  
 #  Set : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> ||Key| |
> ||Value| |
> ``` lang=cpp, name=Zilch
> function Set( : Key,  : Value) : Boolean
> ``` 


---  
 #  SetOrError : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ||Key| |
> ||Value| |
> ``` lang=cpp, name=Zilch
> function SetOrError( : Key,  : Value)
> ``` 


---  
 #  SetOrIgnore : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> ||Key| |
> ||Value| |
> ``` lang=cpp, name=Zilch
> function SetOrIgnore( : Key,  : Value) : Boolean
> ``` 


---  
 #  SetOrOverwrite : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> ||Key| |
> ||Value| |
> ``` lang=cpp, name=Zilch
> function SetOrOverwrite( : Key,  : Value) : Boolean
> ``` 


---  
 

 