 `Physics`

(NOTE) A result from a cast operation on a PhysicsSpace.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/castresult.markdown#castresult-void)|[ Collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/castresult.markdown#collider-zero-engine-doc)| | |
|[ GetLocalPosition](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/castresult.markdown#getlocalposition-zero-en)|[ Distance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/castresult.markdown#distance-zero-engine-doc)| | |
| |[ Normal](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/castresult.markdown#normal-zero-engine-docum)| | |
| |[ ObjectHit](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/castresult.markdown#objecthit-zero-engine-do)| | |
| |[ WorldPosition](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/castresult.markdown#worldposition-zero-engin)| | |


 #  Properties


---  
 #  Collider : [collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collider.markdown)

 `read-only`

> The collider hit by the cast.
> ``` lang=cpp, name=Zilch
> var Collider : Collider


---  
 #  Distance : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

 `read-only`

> The distance from the ray/segment start to the point of intersection. Invalid on a volume cast.
> ``` lang=cpp, name=Zilch
> var Distance : Real


---  
 #  Normal : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

 `read-only`

> The normal of the object at the intersection point (world space). Invalid on a volume cast.
> ``` lang=cpp, name=Zilch
> var Normal : Real3


---  
 #  ObjectHit : [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)

 `read-only`

> The cog hit by the cast.
> ``` lang=cpp, name=Zilch
> var ObjectHit : Cog


---  
 #  WorldPosition : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

 `read-only`

> Returns the world-space position that the object was hit. Invalid on a volume cast.
> ``` lang=cpp, name=Zilch
> var WorldPosition : Real3


---  
 #  Methods


---  
 #  CastResult : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function CastResult()
> ``` 


---  
 #  CastResult : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> |rhs|[castresult](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/castresult.markdown)| |
> ``` lang=cpp, name=Zilch
> function CastResult(rhs : CastResult)
> ``` 


---  
 #  GetLocalPosition : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> Returns the local-space position that the object was hit. The point index is used to get the first or last point of intersection. Invalid on volume casts.
> |Name|Type|Description|
> |---|---|---|
> |pointIndex|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetLocalPosition(pointIndex : Integer) : Real3
> ``` 


---  
 

 