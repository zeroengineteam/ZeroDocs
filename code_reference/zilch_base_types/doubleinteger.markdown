 `Core`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Parse](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/doubleinteger.markdown#parse-zero-engine-docume)|[ NegativeMin](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/doubleinteger.markdown#negativemin-zero-engine)| | |
| |[ NegativeValueClosestToZero](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/doubleinteger.markdown#negativevalueclosesttoze)| | |
| |[ PositiveMax](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/doubleinteger.markdown#positivemax-zero-engine)| | |
| |[ PositiveValueClosestToZero](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/doubleinteger.markdown#positivevalueclosesttoze)| | |


 #  Properties


---  
 #  NegativeMin : [doubleinteger](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/doubleinteger.markdown)

 `read-only` `static`

> The smallest (most negative) value that can be represented by a DoubleInteger.
> ``` lang=cpp, name=Zilch
> var NegativeMin : DoubleInteger


---  
 #  NegativeValueClosestToZero : [doubleinteger](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/doubleinteger.markdown)

 `read-only` `static`

> The negative value closest to zero that can be represented by a DoubleInteger.
> ``` lang=cpp, name=Zilch
> var NegativeValueClosestToZero : DoubleInteger


---  
 #  PositiveMax : [doubleinteger](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/doubleinteger.markdown)

 `read-only` `static`

> The largest (most positive) value that can be represented by a DoubleInteger.
> ``` lang=cpp, name=Zilch
> var PositiveMax : DoubleInteger


---  
 #  PositiveValueClosestToZero : [doubleinteger](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/doubleinteger.markdown)

 `read-only` `static`

> The positive value closest to zero that can be represented by a DoubleInteger.
> ``` lang=cpp, name=Zilch
> var PositiveValueClosestToZero : DoubleInteger


---  
 #  Methods


---  
 #  Parse : [doubleinteger](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/doubleinteger.markdown)

 `static`

> Attempt to convert the given StringRange to a DoubleInteger. If parsing fails 0 is returned.
> |Name|Type|Description|
> |---|---|---|
> |p0|[stringrange](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/stringrange.markdown)| |
> ``` lang=cpp, name=Zilch
> function Parse(p0 : StringRange) : DoubleInteger
> ``` 


---  
 

 