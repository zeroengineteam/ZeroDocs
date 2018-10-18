 `Core`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Get](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown#get-zero-engine-document)|[ Count](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown#count-zero-engine-docume)| | |
|[ GetAxis](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown#getaxis-zero-engine-docu)|[ NegativeMin](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown#negativemin-zero-engine)| | |
|[ Constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown#integer2-void)|[ NegativeValueClosestToZero](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown#negativevalueclosesttoze)| | |
|[ Set](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown#set-void)|[ One](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown#one-zero-engine-document)| | |
| |[ PositiveMax](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown#positivemax-zero-engine)| | |
| |[ PositiveValueClosestToZero](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown#positivevalueclosesttoze)| | |
| |[ XAxis](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown#xaxis-zero-engine-docume)| | |
| |[ YAxis](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown#yaxis-zero-engine-docume)| | |
| |[ Zero](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown#zero-zero-engine-documen)| | |


 #  Properties


---  
 #  Count : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var Count : Integer


---  
 #  NegativeMin : [integer2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown)

 `read-only` `static`

> The smallest (most negative) value that can be represented by an Integer.
> ``` lang=cpp, name=Zilch
> var NegativeMin : Integer2


---  
 #  NegativeValueClosestToZero : [integer2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown)

 `read-only` `static`

> The negative value closest to zero that can be represented by an Integer.
> ``` lang=cpp, name=Zilch
> var NegativeValueClosestToZero : Integer2


---  
 #  One : [integer2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown)

 `read-only` `static`

> The one vector (a vector containing all ones).
> ``` lang=cpp, name=Zilch
> var One : Integer2


---  
 #  PositiveMax : [integer2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown)

 `read-only` `static`

> The largest (most positive) value that can be represented by an Integer.
> ``` lang=cpp, name=Zilch
> var PositiveMax : Integer2


---  
 #  PositiveValueClosestToZero : [integer2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown)

 `read-only` `static`

> The positive value closest to zero that can be represented by an Integer.
> ``` lang=cpp, name=Zilch
> var PositiveValueClosestToZero : Integer2


---  
 #  XAxis : [integer2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown)

 `read-only` `static`

> 
> ``` lang=cpp, name=Zilch
> var XAxis : Integer2


---  
 #  YAxis : [integer2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown)

 `read-only` `static`

> 
> ``` lang=cpp, name=Zilch
> var YAxis : Integer2


---  
 #  Zero : [integer2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown)

 `read-only` `static`

> The zero vector (a vector containing all zeroes).
> ``` lang=cpp, name=Zilch
> var Zero : Integer2


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
 #  GetAxis : [integer2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown)

 `static`

> Returns an axis vector from the given index (ie. 0 is XAxis, 1 is YAxis, etc...
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetAxis(p0 : Integer) : Integer2
> ``` 


---  
 #  Integer2 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Integer2()
> ``` 


---  
 #  Integer2 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |scalar|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Integer2(scalar : Integer)
> ``` 


---  
 #  Integer2 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |p1|[integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Integer2(p0 : Integer, p1 : Integer)
> ``` 


---  
 #  Integer2 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer2](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer2.markdown)| |
> ``` lang=cpp, name=Zilch
> function Integer2(p0 : Integer2)
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
 
  
  
  
  
  
  
  

 