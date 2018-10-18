 `Component` `Physics`



(NOTE) Applies a force about an axis at the object's center. This will apply two forces to a body: One pulls the object towards the center of the vortex and the other applies a tangential force. Useful to model a vortex. This only expects to be used as a Region effect.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vortexeffect.markdown#vortexeffect-void)|[ EndCondition](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vortexeffect.markdown#endcondition-zero-engine)|[physicseffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicseffect.markdown)| |
| |[ InterpolationType](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vortexeffect.markdown#interpolationtype-zero-e)| | |
| |[ InwardStrengthAtMaxDistance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vortexeffect.markdown#inwardstrengthatmaxdista)| | |
| |[ InwardStrengthAtMinDistance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vortexeffect.markdown#inwardstrengthatmindista)| | |
| |[ LocalAxis](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vortexeffect.markdown#localaxis-zero-engine-do)| | |
| |[ MaxDistance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vortexeffect.markdown#maxdistance-zero-engine)| | |
| |[ MinDistance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vortexeffect.markdown#mindistance-zero-engine)| | |
| |[ TwistStrengthAtMaxDistance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vortexeffect.markdown#twiststrengthatmaxdistan)| | |
| |[ TwistStrengthAtMinDistance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vortexeffect.markdown#twiststrengthatmindistan)| | |
| |[ VortexAxis](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vortexeffect.markdown#vortexaxis-zero-engine-d)| | |
| |[ WorldVortexAxis](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/vortexeffect.markdown#worldvortexaxis-zero-eng)| | |


 #  Properties


---  
 #  EndCondition : [PhysicsEffectEndCondition](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#physicseffectendcondition)

> How the interpolation should be handled at MaxDistance. ClampToMax will clamp to the max strength values. NoEffect will ignore the effect. ContinueFalloff will continue the interpolation (this may go negative).
> ``` lang=cpp, name=Zilch
> var EndCondition : PhysicsEffectEndCondition


---  
 #  InterpolationType : [PhysicsEffectInterpolationType](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#physicseffectinterpolationtype)

> The type of interpolation used (e.g. Linear, Quadratic) for the forces.
> ``` lang=cpp, name=Zilch
> var InterpolationType : PhysicsEffectInterpolationType


---  
 #  InwardStrengthAtMaxDistance : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The inward strength of the vortex at the max distance.
> ``` lang=cpp, name=Zilch
> var InwardStrengthAtMaxDistance : Real


---  
 #  InwardStrengthAtMinDistance : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The inward strength of the vortex at the min distance.
> ``` lang=cpp, name=Zilch
> var InwardStrengthAtMinDistance : Real


---  
 #  LocalAxis : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Determines if the vortex axis is in world or local space.
> ``` lang=cpp, name=Zilch
> var LocalAxis : Boolean


---  
 #  MaxDistance : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The max distance that attenuation will happen at. If an object is between min and max distance, the value will be attenuated. If the object is further away, the effect strength will be determined by EndCondition.
> ``` lang=cpp, name=Zilch
> var MaxDistance : Real


---  
 #  MinDistance : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The first distance at which attenuation will start. If an object is under the min distance, the min strength values will be used. If an object is in between min and max, then it will attenuate.
> ``` lang=cpp, name=Zilch
> var MinDistance : Real


---  
 #  TwistStrengthAtMaxDistance : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The perpendicular strength (twist) of the vortex at max distance.
> ``` lang=cpp, name=Zilch
> var TwistStrengthAtMaxDistance : Real


---  
 #  TwistStrengthAtMinDistance : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The perpendicular strength (twist) of the vortex at min distance.
> ``` lang=cpp, name=Zilch
> var TwistStrengthAtMinDistance : Real


---  
 #  VortexAxis : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> The axis the vortex spins about.
> ``` lang=cpp, name=Zilch
> var VortexAxis : Real3


---  
 #  WorldVortexAxis : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

 `read-only`

> The axis the vortex spins about in world space.
> ``` lang=cpp, name=Zilch
> var WorldVortexAxis : Real3


---  
 #  Methods


---  
 #  VortexEffect : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function VortexEffect()
> ``` 


---  
 

 