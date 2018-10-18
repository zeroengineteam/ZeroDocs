 `Component` `Gameplay`



|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splineparticleanimator.markdown#splineparticleanimator-v)|[ AutoCalculateLifetime](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splineparticleanimator.markdown#autocalculatelifetime-ze)|[particleanimator](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleanimator.markdown)| |
| |[ Helix](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splineparticleanimator.markdown#helix-zero-engine-docume)| | |
| |[ HelixOffset](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splineparticleanimator.markdown#helixoffset-zero-engine)| | |
| |[ HelixRadius](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splineparticleanimator.markdown#helixradius-zero-engine)| | |
| |[ HelixWaveLength](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splineparticleanimator.markdown#helixwavelength-zero-eng)| | |
| |[ Mode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splineparticleanimator.markdown#mode-zero-engine-documen)| | |
| |[ Speed](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splineparticleanimator.markdown#speed-zero-engine-docume)| | |
| |[ SpringDampingRatio](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splineparticleanimator.markdown#springdampingratio-zero)| | |
| |[ SpringFrequencyHz](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splineparticleanimator.markdown#springfrequencyhz-zero-e)| | |


 #  Properties


---  
 #  AutoCalculateLifetime : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> If checked, the lifetime on the SplineParticleEmitter will be updated to the time it would take to travel the entire path at the current speed.
> ``` lang=cpp, name=Zilch
> var AutoCalculateLifetime : Boolean


---  
 #  Helix : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Helix : Boolean


---  
 #  HelixOffset : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> Offset in radians for where the helix starts.
> ``` lang=cpp, name=Zilch
> var HelixOffset : Real


---  
 #  HelixRadius : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The radius of the helix.
> ``` lang=cpp, name=Zilch
> var HelixRadius : Real


---  
 #  HelixWaveLength : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> How fast the helix rotates in radians / second.
> ``` lang=cpp, name=Zilch
> var HelixWaveLength : Real


---  
 #  Mode : [SplineAnimatorMode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#splineanimatormode)

> The current animate mode.
> ``` lang=cpp, name=Zilch
> var Mode : SplineAnimatorMode


---  
 #  Speed : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The speed at which the particles move in meters / second.
> ``` lang=cpp, name=Zilch
> var Speed : Real


---  
 #  SpringDampingRatio : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> 
> ``` lang=cpp, name=Zilch
> var SpringDampingRatio : Real


---  
 #  SpringFrequencyHz : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> Spring properties.
> ``` lang=cpp, name=Zilch
> var SpringFrequencyHz : Real


---  
 #  Methods


---  
 #  SplineParticleAnimator : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function SplineParticleAnimator()
> ``` 


---  
 

 