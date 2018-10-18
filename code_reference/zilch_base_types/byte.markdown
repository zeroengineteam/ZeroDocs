 `Core`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Parse](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/byte.markdown#parse-zero-engine-docume)|[ PositiveMax](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/byte.markdown#positivemax-zero-engine)| | |
| |[ PositiveValueClosestToZero](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/byte.markdown#positivevalueclosesttoze)| | |


 #  Properties


---  
 #  PositiveMax : [byte](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/byte.markdown)

 `read-only` `static`

> The largest (most positive) value that can be represented by a Byte.
> ``` lang=cpp, name=Zilch
> var PositiveMax : Byte


---  
 #  PositiveValueClosestToZero : [byte](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/byte.markdown)

 `read-only` `static`

> The positive value closest to zero that can be represented by a Byte.
> ``` lang=cpp, name=Zilch
> var PositiveValueClosestToZero : Byte


---  
 #  Methods


---  
 #  Parse : [byte](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/byte.markdown)

 `static`

> Attempt to convert the given StringRange to a Byte. If parsing fails 0 is returned.
> |Name|Type|Description|
> |---|---|---|
> |p0|[stringrange](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/stringrange.markdown)| |
> ``` lang=cpp, name=Zilch
> function Parse(p0 : StringRange) : Byte
> ``` 


---  
 

 