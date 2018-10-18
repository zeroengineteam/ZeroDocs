 `Core`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Get](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown#get-zero-engine-document)|[ Count](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown#count-zero-engine-docume)| | |
|[ GetAxis](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown#getaxis-zero-engine-docu)|[ NegativeMin](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown#negativemin-zero-engine)| | |
|[ Constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown#integer3-void)|[ NegativeValueClosestToZero](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown#negativevalueclosesttoze)| | |
|[ Set](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown#set-void)|[ One](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown#one-zero-engine-document)| | |
| |[ PositiveMax](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown#positivemax-zero-engine)| | |
| |[ PositiveValueClosestToZero](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown#positivevalueclosesttoze)| | |
| |[ XAxis](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown#xaxis-zero-engine-docume)| | |
| |[ YAxis](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown#yaxis-zero-engine-docume)| | |
| |[ ZAxis](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown#zaxis-zero-engine-docume)| | |
| |[ Zero](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown#zero-zero-engine-documen)| | |


 #  Properties


---  
 #  Count : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var Count : Integer


---  
 #  NegativeMin : [integer3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown)

 `read-only` `static`

> The smallest (most negative) value that can be represented by an Integer.
> ``` lang=cpp, name=Zilch
> var NegativeMin : Integer3


---  
 #  NegativeValueClosestToZero : [integer3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown)

 `read-only` `static`

> The negative value closest to zero that can be represented by an Integer.
> ``` lang=cpp, name=Zilch
> var NegativeValueClosestToZero : Integer3


---  
 #  One : [integer3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown)

 `read-only` `static`

> The one vector (a vector containing all ones).
> ``` lang=cpp, name=Zilch
> var One : Integer3


---  
 #  PositiveMax : [integer3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown)

 `read-only` `static`

> The largest (most positive) value that can be represented by an Integer.
> ``` lang=cpp, name=Zilch
> var PositiveMax : Integer3


---  
 #  PositiveValueClosestToZero : [integer3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown)

 `read-only` `static`

> The positive value closest to zero that can be represented by an Integer.
> ``` lang=cpp, name=Zilch
> var PositiveValueClosestToZero : Integer3


---  
 #  XAxis : [integer3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown)

 `read-only` `static`

> 
> ``` lang=cpp, name=Zilch
> var XAxis : Integer3


---  
 #  YAxis : [integer3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown)

 `read-only` `static`

> 
> ``` lang=cpp, name=Zilch
> var YAxis : Integer3


---  
 #  ZAxis : [integer3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown)

 `read-only` `static`

> 
> ``` lang=cpp, name=Zilch
> var ZAxis : Integer3


---  
 #  Zero : [integer3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown)

 `read-only` `static`

> The zero vector (a vector containing all zeroes).
> ``` lang=cpp, name=Zilch
> var Zero : Integer3


---  
 #  Methods


---  
 #  Get : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Get(p0 : Integer) : Integer
> ``` 


---  
 #  GetAxis : [integer3](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer3.markdown)

 `static`

> Returns an axis vector from the given index (ie. 0 is XAxis, 1 is YAxis, etc...
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetAxis(p0 : Integer) : Integer3
> ``` 


---  
 #  Integer3 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Integer3()
> ``` 


---  
 #  Integer3 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |scalar|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Integer3(scalar : Integer)
> ``` 


---  
 #  Integer3 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |p1|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |p2|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Integer3(p0 : Integer, p1 : Integer, p2 : Integer)
> ``` 


---  
 #  Integer3 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |p1|[integer2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown)| |
> ``` lang=cpp, name=Zilch
> function Integer3(p0 : Integer, p1 : Integer2)
> ``` 


---  
 #  Integer3 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown)| |
> |p1|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Integer3(p0 : Integer2, p1 : Integer)
> ``` 


---  
 #  Set : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |p1|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Set(p0 : Integer, p1 : Integer)
> ``` 


---  
 
  
  
  
  
  
  
  

 