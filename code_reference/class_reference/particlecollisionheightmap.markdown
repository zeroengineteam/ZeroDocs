 `Component` `Graphics`



|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/particlecollisionheightmap.markdown#particlecollisionheightm)|[ Friction](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/particlecollisionheightmap.markdown#friction-zero-engine-doc)|[particleanimator](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/particleanimator.markdown)| |
| |[ HeightMap](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/particlecollisionheightmap.markdown#heightmap-zero-engine-do)| | |
| |[ Restitution](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/particlecollisionheightmap.markdown#restitution-zero-engine)| | |


 #  Properties


---  
 #  Friction : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> How slippery or rough the particle is. When friction is 0, the object will be slippery. When friction is 1, it will completely stop in the direction tangential to the collision normal.
> ``` lang=cpp, name=Zilch
> var Friction : Real


---  
 #  HeightMap : [cogpath](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/cogpath.markdown)

> 
> ``` lang=cpp, name=Zilch
> var HeightMap : CogPath


---  
 #  Restitution : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> How much the particle will bounce during a collision. Values should be in the range of [0, 1], where 0 is an in-elastic collision and 1 is a fully elastic collision (bouncy). If the value is greater than 1, the particle will gain energy and move faster after the bounce.
> ``` lang=cpp, name=Zilch
> var Restitution : Real


---  
 #  Methods


---  
 #  ParticleCollisionHeightmap : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ParticleCollisionHeightmap()
> ``` 


---  
 

 