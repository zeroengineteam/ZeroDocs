 `Core`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Get](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown#get-zero-engine-document)|[ Count](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown#count-zero-engine-docume)| | |
|[ GetAxis](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown#getaxis-zero-engine-docu)|[ NegativeMin](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown#negativemin-zero-engine)| | |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown#real4-void)|[ NegativeValueClosestToZero](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown#negativevalueclosesttoze)| | |
|[ Set](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown#set-void)|[ One](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown#one-zero-engine-document)| | |
| |[ PositiveMax](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown#positivemax-zero-engine)| | |
| |[ PositiveValueClosestToZero](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown#positivevalueclosesttoze)| | |
| |[ WAxis](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown#waxis-zero-engine-docume)| | |
| |[ XAxis](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown#xaxis-zero-engine-docume)| | |
| |[ YAxis](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown#yaxis-zero-engine-docume)| | |
| |[ ZAxis](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown#zaxis-zero-engine-docume)| | |
| |[ Zero](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown#zero-zero-engine-documen)| | |


 #  Properties


---  
 #  Count : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var Count : Integer


---  
 #  NegativeMin : [real4](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown)

 `read-only` `static`

> The smallest (most negative) value that can be represented by a Real.
> ``` lang=cpp, name=Zilch
> var NegativeMin : Real4


---  
 #  NegativeValueClosestToZero : [real4](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown)

 `read-only` `static`

> The negative value closest to zero that can be represented by a Real.
> ``` lang=cpp, name=Zilch
> var NegativeValueClosestToZero : Real4


---  
 #  One : [real4](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown)

 `read-only` `static`

> The one vector (a vector containing all ones).
> ``` lang=cpp, name=Zilch
> var One : Real4


---  
 #  PositiveMax : [real4](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown)

 `read-only` `static`

> The largest (most positive) value that can be represented by a Real.
> ``` lang=cpp, name=Zilch
> var PositiveMax : Real4


---  
 #  PositiveValueClosestToZero : [real4](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown)

 `read-only` `static`

> The positive value closest to zero that can be represented by a Real.
> ``` lang=cpp, name=Zilch
> var PositiveValueClosestToZero : Real4


---  
 #  WAxis : [real4](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown)

 `read-only` `static`

> 
> ``` lang=cpp, name=Zilch
> var WAxis : Real4


---  
 #  XAxis : [real4](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown)

 `read-only` `static`

> 
> ``` lang=cpp, name=Zilch
> var XAxis : Real4


---  
 #  YAxis : [real4](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown)

 `read-only` `static`

> 
> ``` lang=cpp, name=Zilch
> var YAxis : Real4


---  
 #  ZAxis : [real4](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown)

 `read-only` `static`

> 
> ``` lang=cpp, name=Zilch
> var ZAxis : Real4


---  
 #  Zero : [real4](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown)

 `read-only` `static`

> The zero vector (a vector containing all zeroes).
> ``` lang=cpp, name=Zilch
> var Zero : Real4


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
 #  GetAxis : [real4](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real4.markdown)

 `static`

> Returns an axis vector from the given index (ie. 0 is XAxis, 1 is YAxis, etc...
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetAxis(p0 : Integer) : Real4
> ``` 


---  
 #  Real4 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Real4()
> ``` 


---  
 #  Real4 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |scalar|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Real4(scalar : Real)
> ``` 


---  
 #  Real4 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |p1|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |p2|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |p3|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Real4(p0 : Real, p1 : Real, p2 : Real, p3 : Real)
> ``` 


---  
 #  Real4 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |p1|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |p2|[real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)| |
> ``` lang=cpp, name=Zilch
> function Real4(p0 : Real, p1 : Real, p2 : Real2)
> ``` 


---  
 #  Real4 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |p1|[real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)| |
> |p2|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Real4(p0 : Real, p1 : Real2, p2 : Real)
> ``` 


---  
 #  Real4 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |p1|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function Real4(p0 : Real, p1 : Real3)
> ``` 


---  
 #  Real4 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)| |
> |p1|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |p2|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Real4(p0 : Real2, p1 : Real, p2 : Real)
> ``` 


---  
 #  Real4 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)| |
> |p1|[real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)| |
> ``` lang=cpp, name=Zilch
> function Real4(p0 : Real2, p1 : Real2)
> ``` 


---  
 #  Real4 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |p1|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Real4(p0 : Real3, p1 : Real)
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
 

 