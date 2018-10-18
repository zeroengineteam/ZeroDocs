 `Core`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Add](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#add-void)|[ All](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#all-zero-engine-document)| | |
|[ Constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#array-t-void)|[ Capacity](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#capacity-zero-engine-doc)| | |
|[ Clear](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#clear-void)|[ Count](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#count-zero-engine-docume)| | |
|[ Copy](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#copy-zero-engine-documen)|[ LastIndex](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#lastindex-zero-engine-do)| | |
|[ FindFirstIndex](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#findfirstindex-zero-engi)| | | |
|[ Get](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#get-zero-engine-document)| | | |
|[ Insert](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#insert-void)| | | |
|[ Pop](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#pop-zero-engine-document)| | | |
|[ Push](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#push-void)| | | |
|[ Range](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#range-zero-engine-docume)| | | |
|[ RemoveAll](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#removeall-zero-engine-do)| | | |
|[ RemoveAt](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#removeat-void)| | | |
|[ RemoveFirst](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#removefirst-zero-engine)| | | |
|[ RemoveSwap](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#removeswap-void)| | | |
|[ Reserve](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#reserve-void)| | | |
|[ Resize](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#resize-void)| | | |
|[ Set](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#set-void)| | | |
|[ Sort](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/array_t .markdown#sort-void)| | | |


 #  Properties


---  
 #  All : ArrayRange[T]

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var All : ArrayRange[T]


---  
 #  Capacity : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var Capacity : Integer


---  
 #  Count : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var Count : Integer


---  
 #  LastIndex : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var LastIndex : Integer


---  
 #  Methods


---  
 #  Add : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|T| |
> ``` lang=cpp, name=Zilch
> function Add(p0 : T)
> ``` 


---  
 #  Array[T] : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Array[T]()
> ``` 


---  
 #  Array[T] : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |size|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Array[T](size : Integer)
> ``` 


---  
 #  Array[T] : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |size|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |defaultValue|T| |
> ``` lang=cpp, name=Zilch
> function Array[T](size : Integer, defaultValue : T)
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
 #  Copy : Array[T]

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Copy() : Array[T]
> ``` 


---  
 #  FindFirstIndex : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |value|T| |
> ``` lang=cpp, name=Zilch
> function FindFirstIndex(value : T) : Integer
> ``` 


---  
 #  Get : T

> 
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Get(index : Integer) : T
> ``` 


---  
 #  Insert : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |value|T| |
> ``` lang=cpp, name=Zilch
> function Insert(index : Integer, value : T)
> ``` 


---  
 #  Pop : T

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Pop() : T
> ``` 


---  
 #  Push : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|T| |
> ``` lang=cpp, name=Zilch
> function Push(p0 : T)
> ``` 


---  
 #  Range : ArrayRange[T]

> 
> |Name|Type|Description|
> |---|---|---|
> |start|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |count|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Range(start : Integer, count : Integer) : ArrayRange[T]
> ``` 


---  
 #  RemoveAll : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |value|T| |
> ``` lang=cpp, name=Zilch
> function RemoveAll(value : T) : Integer
> ``` 


---  
 #  RemoveAt : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function RemoveAt(index : Integer)
> ``` 


---  
 #  RemoveFirst : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |value|T| |
> ``` lang=cpp, name=Zilch
> function RemoveFirst(value : T) : Boolean
> ``` 


---  
 #  RemoveSwap : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function RemoveSwap(index : Integer)
> ``` 


---  
 #  Reserve : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |capacity|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Reserve(capacity : Integer)
> ``` 


---  
 #  Resize : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |size|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Resize(size : Integer)
> ``` 


---  
 #  Resize : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |size|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |defaultValue|T| |
> ``` lang=cpp, name=Zilch
> function Resize(size : Integer, defaultValue : T)
> ``` 


---  
 #  Set : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |value|T| |
> ``` lang=cpp, name=Zilch
> function Set(index : Integer, value : T)
> ``` 


---  
 #  Sort : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |compare|delegate(left:any,right:any):[boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)| |
> ``` lang=cpp, name=Zilch
> function Sort(compare : delegate(left:any,right:any):Boolean)
> ``` 


---  
 #  Sort : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |compare|delegate(left:any,right:any):[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Sort(compare : delegate(left:any,right:any):Integer)
> ``` 


---  
 
  
  
  
  
  
  
  

 