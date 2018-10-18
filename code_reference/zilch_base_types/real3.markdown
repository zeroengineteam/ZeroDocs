 `Core`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Get](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown#get-zero-engine-document)|[ Count](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown#count-zero-engine-docume)| | |
|[ GetAxis](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown#getaxis-zero-engine-docu)|[ NegativeMin](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown#negativemin-zero-engine)| | |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown#real3-void)|[ NegativeValueClosestToZero](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown#negativevalueclosesttoze)| | |
|[ Set](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown#set-void)|[ One](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown#one-zero-engine-document)| | |
| |[ PositiveMax](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown#positivemax-zero-engine)| | |
| |[ PositiveValueClosestToZero](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown#positivevalueclosesttoze)| | |
| |[ XAxis](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown#xaxis-zero-engine-docume)| | |
| |[ YAxis](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown#yaxis-zero-engine-docume)| | |
| |[ ZAxis](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown#zaxis-zero-engine-docume)| | |
| |[ Zero](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown#zero-zero-engine-documen)| | |


 #  Properties


---  
 #  Count : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var Count : Integer


---  
 #  NegativeMin : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only` `static`

> The smallest (most negative) value that can be represented by a Real.
> ``` lang=cpp, name=Zilch
> var NegativeMin : Real3


---  
 #  NegativeValueClosestToZero : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only` `static`

> The negative value closest to zero that can be represented by a Real.
> ``` lang=cpp, name=Zilch
> var NegativeValueClosestToZero : Real3


---  
 #  One : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only` `static`

> The one vector (a vector containing all ones).
> ``` lang=cpp, name=Zilch
> var One : Real3


---  
 #  PositiveMax : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only` `static`

> The largest (most positive) value that can be represented by a Real.
> ``` lang=cpp, name=Zilch
> var PositiveMax : Real3


---  
 #  PositiveValueClosestToZero : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only` `static`

> The positive value closest to zero that can be represented by a Real.
> ``` lang=cpp, name=Zilch
> var PositiveValueClosestToZero : Real3


---  
 #  XAxis : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only` `static`

> 
> ``` lang=cpp, name=Zilch
> var XAxis : Real3


---  
 #  YAxis : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only` `static`

> 
> ``` lang=cpp, name=Zilch
> var YAxis : Real3


---  
 #  ZAxis : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only` `static`

> 
> ``` lang=cpp, name=Zilch
> var ZAxis : Real3


---  
 #  Zero : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `read-only` `static`

> The zero vector (a vector containing all zeroes).
> ``` lang=cpp, name=Zilch
> var Zero : Real3


---  
 #  Methods


---  
 #  Get : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Get(p0 : Integer) : Real
> ``` 


---  
 #  GetAxis : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

 `static`

> Returns an axis vector from the given index (ie. 0 is XAxis, 1 is YAxis, etc...
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetAxis(p0 : Integer) : Real3
> ``` 


---  
 #  Real3 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Real3()
> ``` 


---  
 #  Real3 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |scalar|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Real3(scalar : Real)
> ``` 


---  
 #  Real3 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |p1|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |p2|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Real3(p0 : Real, p1 : Real, p2 : Real)
> ``` 


---  
 #  Real3 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |p1|[real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)| |
> ``` lang=cpp, name=Zilch
> function Real3(p0 : Real, p1 : Real2)
> ``` 


---  
 #  Real3 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)| |
> |p1|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Real3(p0 : Real2, p1 : Real)
> ``` 


---  
 #  Set : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> |p1|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Set(p0 : Integer, p1 : Real)
> ``` 


---  
 

 