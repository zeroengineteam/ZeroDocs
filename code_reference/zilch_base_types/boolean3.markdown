 `Core`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean3.markdown#boolean3-void)|[ Count](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean3.markdown#count-zero-engine-docume)| | |
|[ Get](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean3.markdown#get-zero-engine-document)|[ One](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean3.markdown#one-zero-engine-document)| | |
|[ GetAxis](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean3.markdown#getaxis-zero-engine-docu)|[ XAxis](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean3.markdown#xaxis-zero-engine-docume)| | |
|[ Set](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean3.markdown#set-void)|[ YAxis](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean3.markdown#yaxis-zero-engine-docume)| | |
| |[ ZAxis](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean3.markdown#zaxis-zero-engine-docume)| | |
| |[ Zero](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean3.markdown#zero-zero-engine-documen)| | |


 #  Properties


---  
 #  Count : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> 
> ``` lang=cpp, name=Zilch
> var Count : Integer


---  
 #  One : [boolean3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean3.markdown)

 `read-only` `static`

> The one vector (a vector containing all ones).
> ``` lang=cpp, name=Zilch
> var One : Boolean3


---  
 #  XAxis : [boolean3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean3.markdown)

 `read-only` `static`

> 
> ``` lang=cpp, name=Zilch
> var XAxis : Boolean3


---  
 #  YAxis : [boolean3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean3.markdown)

 `read-only` `static`

> 
> ``` lang=cpp, name=Zilch
> var YAxis : Boolean3


---  
 #  ZAxis : [boolean3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean3.markdown)

 `read-only` `static`

> 
> ``` lang=cpp, name=Zilch
> var ZAxis : Boolean3


---  
 #  Zero : [boolean3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean3.markdown)

 `read-only` `static`

> The zero vector (a vector containing all zeroes).
> ``` lang=cpp, name=Zilch
> var Zero : Boolean3


---  
 #  Methods


---  
 #  Boolean3 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Boolean3()
> ``` 


---  
 #  Boolean3 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |scalar|[boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)| |
> ``` lang=cpp, name=Zilch
> function Boolean3(scalar : Boolean)
> ``` 


---  
 #  Boolean3 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)| |
> |p1|[boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)| |
> |p2|[boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)| |
> ``` lang=cpp, name=Zilch
> function Boolean3(p0 : Boolean, p1 : Boolean, p2 : Boolean)
> ``` 


---  
 #  Boolean3 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)| |
> |p1|[boolean2](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean2.markdown)| |
> ``` lang=cpp, name=Zilch
> function Boolean3(p0 : Boolean, p1 : Boolean2)
> ``` 


---  
 #  Boolean3 : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[boolean2](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean2.markdown)| |
> |p1|[boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)| |
> ``` lang=cpp, name=Zilch
> function Boolean3(p0 : Boolean2, p1 : Boolean)
> ``` 


---  
 #  Get : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function Get(p0 : Integer) : Boolean
> ``` 


---  
 #  GetAxis : [boolean3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean3.markdown)

 `static`

> Returns an axis vector from the given index (ie. 0 is XAxis, 1 is YAxis, etc...
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetAxis(p0 : Integer) : Boolean3
> ``` 


---  
 #  Set : Void

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |p1|[boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)| |
> ``` lang=cpp, name=Zilch
> function Set(p0 : Integer, p1 : Boolean)
> ``` 


---  
 

 