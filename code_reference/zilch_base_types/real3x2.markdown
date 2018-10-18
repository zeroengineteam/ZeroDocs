 `Core`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Get](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3x2.markdown#get-zero-engine-document)|[ Count](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3x2.markdown#count-zero-engine-docume)| | |
|[ GetByIndex](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3x2.markdown#getbyindex-zero-engine-d)|[ CountX](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3x2.markdown#countx-zero-engine-docum)| | |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3x2.markdown#real3x2-void)|[ CountY](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3x2.markdown#county-zero-engine-docum)| | |
|[ Set](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3x2.markdown#set-void)|[ M00](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3x2.markdown#m00-zero-engine-document)| | |
|[ SetByIndex](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3x2.markdown#setbyindex-void)|[ M01](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3x2.markdown#m01-zero-engine-document)| | |
| |[ M10](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3x2.markdown#m10-zero-engine-document)| | |
| |[ M11](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3x2.markdown#m11-zero-engine-document)| | |
| |[ M20](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3x2.markdown#m20-zero-engine-document)| | |
| |[ M21](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3x2.markdown#m21-zero-engine-document)| | |


 #  Properties


---  
 #  Count : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var Count : Integer


---  
 #  CountX : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var CountX : Integer


---  
 #  CountY : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var CountY : Integer


---  
 #  M00 : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> 
> ``` lang=cpp, name=Zilch
> var M00 : Real


---  
 #  M01 : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> 
> ``` lang=cpp, name=Zilch
> var M01 : Real


---  
 #  M10 : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> 
> ``` lang=cpp, name=Zilch
> var M10 : Real


---  
 #  M11 : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> 
> ``` lang=cpp, name=Zilch
> var M11 : Real


---  
 #  M20 : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> 
> ``` lang=cpp, name=Zilch
> var M20 : Real


---  
 #  M21 : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> 
> ``` lang=cpp, name=Zilch
> var M21 : Real


---  
 #  Methods


---  
 #  Get : [real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |y|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Get(y : Integer) : Real2
> ``` 


---  
 #  Get : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |y|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> |x|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Get(y : Integer, x : Integer) : Real
> ``` 


---  
 #  GetByIndex : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetByIndex(index : Integer) : Real
> ``` 


---  
 #  Real3x2 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Real3x2()
> ``` 


---  
 #  Real3x2 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Real3x2(p0 : Real)
> ``` 


---  
 #  Real3x2 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |m00|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |m01|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |m10|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |m11|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |m20|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |m21|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Real3x2(m00 : Real, m01 : Real, m10 : Real, m11 : Real, m20 : Real, m21 : Real)
> ``` 


---  
 #  Set : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |y|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> |x|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> |value|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function Set(y : Integer, x : Integer, value : Real)
> ``` 


---  
 #  Set : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |y|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> |value|[real2](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real2.markdown)| |
> ``` lang=cpp, name=Zilch
> function Set(y : Integer, value : Real2)
> ``` 


---  
 #  SetByIndex : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> |value|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetByIndex(index : Integer, value : Real)
> ``` 


---  
 

 