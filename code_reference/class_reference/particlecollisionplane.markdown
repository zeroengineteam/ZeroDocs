 `Component` `Graphics`



|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particlecollisionplane.markdown#particlecollisionplane-v)|[ Friction](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particlecollisionplane.markdown#friction-zero-engine-doc)|[particleanimator](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleanimator.markdown)| |
| |[ PlaneNormal](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particlecollisionplane.markdown#planenormal-zero-engine)| | |
| |[ PlanePosition](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particlecollisionplane.markdown#planeposition-zero-engin)| | |
| |[ PlaneSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particlecollisionplane.markdown#planespace-zero-engine-d)| | |
| |[ Restitution](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particlecollisionplane.markdown#restitution-zero-engine)| | |


 #  Properties


---  
 #  Friction : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> How slippery or rough the particle is. When friction is 0, the object will be slippery. When friction is 1, it will completely stop in the direction tangential to the collision normal. Values should be in the range [0, 1].
> ``` lang=cpp, name=Zilch
> var Friction : Real


---  
 #  PlaneNormal : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> 
> ``` lang=cpp, name=Zilch
> var PlaneNormal : Real3


---  
 #  PlanePosition : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> 
> ``` lang=cpp, name=Zilch
> var PlanePosition : Real3


---  
 #  PlaneSpace : [SystemSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#systemspace)

> 
> ``` lang=cpp, name=Zilch
> var PlaneSpace : SystemSpace


---  
 #  Restitution : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> How much the particle will bounce during a collision. Values should be in the range of [0, 1], where 0 is an in-elastic collision and 1 is a fully elastic collision (bouncy). If the value is greater than 1, the particle will gain energy and move faster after the bounce.
> ``` lang=cpp, name=Zilch
> var Restitution : Real


---  
 #  Methods


---  
 #  ParticleCollisionPlane : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ParticleCollisionPlane()
> ``` 


---  
 

 