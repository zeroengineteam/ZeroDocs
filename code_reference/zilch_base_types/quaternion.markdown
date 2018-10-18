 `Core`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Get](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/quaternion.markdown#get-zero-engine-document)|[ Count](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/quaternion.markdown#count-zero-engine-docume)| | |
|[ Constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/quaternion.markdown#quaternion-void)|[ Identity](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/quaternion.markdown#identity-zero-engine-doc)| | |
|[ Set](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/quaternion.markdown#set-void)| | | |


 #  Properties


---  
 #  Count : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var Count : Integer


---  
 #  Identity : [quaternion](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/quaternion.markdown)

 `read-only` `static`

> 
> ``` lang=cpp, name=Zilch
> var Identity : Quaternion


---  
 #  Methods


---  
 #  Get : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Get(p0 : Integer) : Real
> ``` 


---  
 #  Quaternion : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Quaternion()
> ``` 


---  
 #  Quaternion : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |scalar|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Quaternion(scalar : Real)
> ``` 


---  
 #  Quaternion : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |p1|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |p2|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |p3|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Quaternion(p0 : Real, p1 : Real, p2 : Real, p3 : Real)
> ``` 


---  
 #  Quaternion : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |p1|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |p2|[real2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real2.markdown)| |
> ``` lang=cpp, name=Zilch
> function Quaternion(p0 : Real, p1 : Real, p2 : Real2)
> ``` 


---  
 #  Quaternion : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |p1|[real2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real2.markdown)| |
> |p2|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Quaternion(p0 : Real, p1 : Real2, p2 : Real)
> ``` 


---  
 #  Quaternion : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |p1|[real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function Quaternion(p0 : Real, p1 : Real3)
> ``` 


---  
 #  Quaternion : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[real2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real2.markdown)| |
> |p1|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |p2|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Quaternion(p0 : Real2, p1 : Real, p2 : Real)
> ``` 


---  
 #  Quaternion : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[real2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real2.markdown)| |
> |p1|[real2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real2.markdown)| |
> ``` lang=cpp, name=Zilch
> function Quaternion(p0 : Real2, p1 : Real2)
> ``` 


---  
 #  Quaternion : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[real3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real3.markdown)| |
> |p1|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Quaternion(p0 : Real3, p1 : Real)
> ``` 


---  
 #  Set : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |p1|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Set(p0 : Integer, p1 : Real)
> ``` 


---  
 
  
  
  
  
  
  
  

 