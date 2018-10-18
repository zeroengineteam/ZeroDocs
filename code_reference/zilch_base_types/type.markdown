 `Core`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ IsA](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/type.markdown#isa-zero-engine-document)|[ IsAny](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/type.markdown#isany-zero-engine-docume)|[reflectionobject](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/reflectionobject.markdown)|[anytype](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/anytype.markdown)|
|[ IsCastableTo](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/type.markdown#iscastableto-zero-engine)|[ IsDelegate](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/type.markdown#isdelegate-zero-engine-d)| |[boundtype](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boundtype.markdown)|
|[ IsRawCastableTo](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/type.markdown#israwcastableto-zero-eng)|[ IsEnum](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/type.markdown#isenum-zero-engine-docum)| |[delegatetype](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/delegatetype.markdown)|
| |[ IsEnumOrFlags](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/type.markdown#isenumorflags-zero-engin)| |[indirectiontype](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/indirectiontype.markdown)|
| |[ IsFlags](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/type.markdown#isflags-zero-engine-docu)| | |
| |[ IsHandle](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/type.markdown#ishandle-zero-engine-doc)| | |
| |[ IsValue](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/type.markdown#isvalue-zero-engine-docu)| | |
| |[ Library](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/type.markdown#library-zero-engine-docu)| | |
| |[ Name](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/type.markdown#name-zero-engine-documen)| | |


 #  Properties


---  
 #  IsAny : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var IsAny : Boolean


---  
 #  IsDelegate : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var IsDelegate : Boolean


---  
 #  IsEnum : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var IsEnum : Boolean


---  
 #  IsEnumOrFlags : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var IsEnumOrFlags : Boolean


---  
 #  IsFlags : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var IsFlags : Boolean


---  
 #  IsHandle : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var IsHandle : Boolean


---  
 #  IsValue : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var IsValue : Boolean


---  
 #  Library : [library](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/library.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var Library : Library


---  
 #  Name : [string](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var Name : String


---  
 #  Methods


---  
 #  IsA : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |baseType|[type](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/type.markdown)| |
> ``` lang=cpp, name=Zilch
> function IsA(baseType : Type) : Boolean
> ``` 


---  
 #  IsCastableTo : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |toType|[type](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/type.markdown)| |
> ``` lang=cpp, name=Zilch
> function IsCastableTo(toType : Type) : Boolean
> ``` 


---  
 #  IsRawCastableTo : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |toType|[type](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/type.markdown)| |
> ``` lang=cpp, name=Zilch
> function IsRawCastableTo(toType : Type) : Boolean
> ``` 


---  
 

 