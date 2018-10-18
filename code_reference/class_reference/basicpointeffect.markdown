 `Component` `Physics`



(NOTE) Common interface for all point effects. Used to attract or repel objects towards a central point. The strength of the effect is calculated as an interpolation between two strength values at two radial distances.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
| |[ EndCondition](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/basicpointeffect.markdown#endcondition-zero-engine)|[physicseffect](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicseffect.markdown)|[pointforceeffect](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/pointforceeffect.markdown)|
| |[ InterpolationType](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/basicpointeffect.markdown#interpolationtype-zero-e)| |[pointgravityeffect](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/pointgravityeffect.markdown)|
| |[ LocalPositionOffset](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/basicpointeffect.markdown#localpositionoffset-zero)| | |
| |[ MaxDistance](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/basicpointeffect.markdown#maxdistance-zero-engine)| | |
| |[ MinDistance](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/basicpointeffect.markdown#mindistance-zero-engine)| | |
| |[ StrengthAtMax](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/basicpointeffect.markdown#strengthatmax-zero-engin)| | |
| |[ StrengthAtMin](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/basicpointeffect.markdown#strengthatmin-zero-engin)| | |


 #  Properties


---  
 #  EndCondition : [PhysicsEffectEndCondition](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#physicseffectendcondition)

> How the interpolation should be handled after max distance. ClampToMax will clamp to StrengthAtMax. NoEffect will ignore the effect. ContinueFalloff will continue the interpolation (this may go negative).
> ``` lang=cpp, name=Zilch
> var EndCondition : PhysicsEffectEndCondition


---  
 #  InterpolationType : [PhysicsEffectInterpolationType](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#physicseffectinterpolationtype)

> The type of interpolation used (e.g. Linear, Quadratic) for the effect.
> ``` lang=cpp, name=Zilch
> var InterpolationType : PhysicsEffectInterpolationType


---  
 #  LocalPositionOffset : [real3](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real3.markdown)

> The offset from the transform position (in local space) that the point effect will be applied at.
> ``` lang=cpp, name=Zilch
> var LocalPositionOffset : Real3


---  
 #  MaxDistance : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The max distance that attenuation will happen at. If an object is between min and max distance, the value will be attenuated. If the object is further away, the effect strength will be determined by EndCondition.
> ``` lang=cpp, name=Zilch
> var MaxDistance : Real


---  
 #  MinDistance : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The first distance at which attenuation will start. If an object is under the min distance, StrengthAtMin will be used. If an object is in between min and max, then it will attenuate.
> ``` lang=cpp, name=Zilch
> var MinDistance : Real


---  
 #  StrengthAtMax : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The strength that this effect applies at the max distance.
> ``` lang=cpp, name=Zilch
> var StrengthAtMax : Real


---  
 #  StrengthAtMin : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The strength that this effect applies at the min distance.
> ``` lang=cpp, name=Zilch
> var StrengthAtMin : Real


---  
 #  Methods


---  
 

 