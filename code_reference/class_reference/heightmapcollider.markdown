 `Component` `Physics`



(NOTE) Defines collision for a height map.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ ClearCachedEdgeAdjacency](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/heightmapcollider.markdown#clearcachededgeadjacency)|[ Thickness](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/heightmapcollider.markdown#thickness-zero-engine-do)|[collider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collider.markdown)| |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/heightmapcollider.markdown#heightmapcollider-void)| | | |


 #  Properties


---  
 #  Thickness : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> How thick the surface of the height map is. Used to avoid tunneling problems.
> ``` lang=cpp, name=Zilch
> var Thickness : Real


---  
 #  Methods


---  
 #  ClearCachedEdgeAdjacency : Void

> Clear the cached information used to avoid catching edges. Typically called internally by physics, but is exposed for manual triggering.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ClearCachedEdgeAdjacency()
> ``` 


---  
 #  HeightMapCollider : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function HeightMapCollider()
> ``` 


---  
 

 