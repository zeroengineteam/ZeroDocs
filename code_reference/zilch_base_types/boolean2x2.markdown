 `Core`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean2x2.markdown#boolean2x2-void)|[ Count](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean2x2.markdown#count-zero-engine-docume)| | |
|[ Get](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean2x2.markdown#get-zero-engine-document)|[ CountX](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean2x2.markdown#countx-zero-engine-docum)| | |
|[ GetByIndex](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean2x2.markdown#getbyindex-zero-engine-d)|[ CountY](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean2x2.markdown#county-zero-engine-docum)| | |
|[ Set](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean2x2.markdown#set-void)|[ M00](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean2x2.markdown#m00-zero-engine-document)| | |
|[ SetByIndex](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean2x2.markdown#setbyindex-void)|[ M01](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean2x2.markdown#m01-zero-engine-document)| | |
| |[ M10](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean2x2.markdown#m10-zero-engine-document)| | |
| |[ M11](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean2x2.markdown#m11-zero-engine-document)| | |


 #  Properties


---  
 #  Count : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var Count : Integer


---  
 #  CountX : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var CountX : Integer


---  
 #  CountY : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var CountY : Integer


---  
 #  M00 : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> ``` lang=cpp, name=Zilch
> var M00 : Boolean


---  
 #  M01 : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> ``` lang=cpp, name=Zilch
> var M01 : Boolean


---  
 #  M10 : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> ``` lang=cpp, name=Zilch
> var M10 : Boolean


---  
 #  M11 : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> ``` lang=cpp, name=Zilch
> var M11 : Boolean


---  
 #  Methods


---  
 #  Boolean2x2 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Boolean2x2()
> ``` 


---  
 #  Boolean2x2 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)| |
> ``` lang=cpp, name=Zilch
> function Boolean2x2(p0 : Boolean)
> ``` 


---  
 #  Boolean2x2 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |m00|[boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)| |
> |m01|[boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)| |
> |m10|[boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)| |
> |m11|[boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)| |
> ``` lang=cpp, name=Zilch
> function Boolean2x2(m00 : Boolean, m01 : Boolean, m10 : Boolean, m11 : Boolean)
> ``` 


---  
 #  Get : [boolean2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean2.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |y|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Get(y : Integer) : Boolean2
> ``` 


---  
 #  Get : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |y|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |x|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Get(y : Integer, x : Integer) : Boolean
> ``` 


---  
 #  GetByIndex : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetByIndex(index : Integer) : Boolean
> ``` 


---  
 #  Set : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |y|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |value|[boolean2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean2.markdown)| |
> ``` lang=cpp, name=Zilch
> function Set(y : Integer, value : Boolean2)
> ``` 


---  
 #  Set : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |y|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |x|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |value|[boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)| |
> ``` lang=cpp, name=Zilch
> function Set(y : Integer, x : Integer, value : Boolean)
> ``` 


---  
 #  SetByIndex : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |value|[boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetByIndex(index : Integer, value : Boolean)
> ``` 


---  
 
  
  
  
  
  
  
  

 