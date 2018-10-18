 `Geometry`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ GetPoint](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ray.markdown#getpoint-zero-engine-doc)|[ Direction](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ray.markdown#direction-zero-engine-do)| | |
|[ GetTValue](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ray.markdown#gettvalue-zero-engine-do)|[ Start](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ray.markdown#start-zero-engine-docume)| | |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ray.markdown#ray-void)| | | |


 #  Properties


---  
 #  Direction : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Direction : Real3


---  
 #  Start : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Start : Real3


---  
 #  Methods


---  
 #  GetPoint : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> Returns the point at the given t-value.
> |Name|Type|Description|
> |---|---|---|
> |tValue|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetPoint(tValue : Real) : Real3
> ``` 


---  
 #  GetTValue : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> Returns the t-value that would result in the given point projected onto the ray.
> |Name|Type|Description|
> |---|---|---|
> |point|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetTValue(point : Real3) : Real
> ``` 


---  
 #  Ray : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Ray()
> ``` 


---  
 #  Ray : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |p0|[ray](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/ray.markdown)| |
> ``` lang=cpp, name=Zilch
> function Ray(p0 : Ray)
> ``` 


---  
 #  Ray : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |start|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> |direction|[real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)| |
> ``` lang=cpp, name=Zilch
> function Ray(start : Real3, direction : Real3)
> ``` 


---  
 

 