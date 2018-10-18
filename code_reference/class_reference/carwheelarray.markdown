 `Physics`

(NOTE) An array interface to the cog paths of wheels that this car uses. This array is read-only.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Get](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/carwheelarray.markdown#get-zero-engine-document)|[ Count](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/carwheelarray.markdown#count-zero-engine-docume)|[safeid32object](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/safeid32object.markdown)| |


 #  Properties


---  
 #  Count : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> How many wheels this car owns.
> ``` lang=cpp, name=Zilch
> var Count : Integer


---  
 #  Methods


---  
 #  Get : [cog](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cog.markdown)

> Get the cog for a wheel by index.
> |Name|Type|Description|
> |---|---|---|
> |index|[integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Get(index : Integer) : Cog
> ``` 


---  
 

 