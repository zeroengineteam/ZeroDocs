 `Core`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Get](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown#get-zero-engine-document)|[ Count](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown#count-zero-engine-docume)| | |
|[ GetAxis](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown#getaxis-zero-engine-docu)|[ NegativeMin](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown#negativemin-zero-engine)| | |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown#integer-void)|[ NegativeValueClosestToZero](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown#negativevalueclosesttoze)| | |
|[ Parse](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown#parse-zero-engine-docume)|[ One](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown#one-zero-engine-document)| | |
|[ Reinterpret](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown#reinterpret-zero-engine)|[ PositiveMax](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown#positivemax-zero-engine)| | |
|[ Set](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown#set-void)|[ PositiveValueClosestToZero](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown#positivevalueclosesttoze)| | |
| |[ XAxis](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown#xaxis-zero-engine-docume)| | |
| |[ Zero](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown#zero-zero-engine-documen)| | |


 #  Properties


---  
 #  Count : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var Count : Integer


---  
 #  NegativeMin : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only` `static`

> The smallest (most negative) value that can be represented by an Integer.
> ``` lang=cpp, name=Zilch
> var NegativeMin : Integer


---  
 #  NegativeValueClosestToZero : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only` `static`

> The negative value closest to zero that can be represented by an Integer.
> ``` lang=cpp, name=Zilch
> var NegativeValueClosestToZero : Integer


---  
 #  One : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only` `static`

> The one vector (a vector containing all ones).
> ``` lang=cpp, name=Zilch
> var One : Integer


---  
 #  PositiveMax : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only` `static`

> The largest (most positive) value that can be represented by an Integer.
> ``` lang=cpp, name=Zilch
> var PositiveMax : Integer


---  
 #  PositiveValueClosestToZero : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only` `static`

> The positive value closest to zero that can be represented by an Integer.
> ``` lang=cpp, name=Zilch
> var PositiveValueClosestToZero : Integer


---  
 #  XAxis : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only` `static`

> 
> ``` lang=cpp, name=Zilch
> var XAxis : Integer


---  
 #  Zero : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only` `static`

> The zero vector (a vector containing all zeroes).
> ``` lang=cpp, name=Zilch
> var Zero : Integer


---  
 #  Methods


---  
 #  Get : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Get(p0 : Integer) : Integer
> ``` 


---  
 #  GetAxis : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `static`

> Returns an axis vector from the given index (ie. 0 is XAxis, 1 is YAxis, etc...
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetAxis(p0 : Integer) : Integer
> ``` 


---  
 #  Integer : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Integer()
> ``` 


---  
 #  Integer : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |scalar|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Integer(scalar : Integer)
> ``` 


---  
 #  Parse : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `static`

> Attempt to convert the given StringRange to an Integer. If parsing fails 0 is returned.
> |Name|Type|Description|
> |---|---|---|
> |p0|[stringrange](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/stringrange.markdown)| |
> ``` lang=cpp, name=Zilch
> function Parse(p0 : StringRange) : Integer
> ``` 


---  
 #  Reinterpret : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `static`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Reinterpret(p0 : Real) : Integer
> ``` 


---  
 #  Set : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> |p1|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Set(p0 : Integer, p1 : Integer)
> ``` 


---  
 

 