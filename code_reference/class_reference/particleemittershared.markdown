 `Component` `Graphics`



(NOTE) Particle Emitter Shared.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ ResetCount](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#resetcount-void)|[ Active](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#active-zero-engine-docum)|[particleemitter](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemitter.markdown)|[boxparticleemitter](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/boxparticleemitter.markdown)|
| |[ EmitCount](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#emitcount-zero-engine-do)| |[meshparticleemitter](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/meshparticleemitter.markdown)|
| |[ EmitDelay](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#emitdelay-zero-engine-do)| |[sphericalparticleemitter](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/sphericalparticleemitter.markdown)|
| |[ EmitRate](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#emitrate-zero-engine-doc)| |[splineparticleemitter](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/splineparticleemitter.markdown)|
| |[ EmitRateSoftStartTime](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#emitratesoftstarttime-ze)| | |
| |[ EmitterSize](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#emittersize-zero-engine)| | |
| |[ EmitterVelocityPercent](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#emittervelocitypercent-z)| | |
| |[ EmitVariance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#emitvariance-zero-engine)| | |
| |[ FastMovingEmitter](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#fastmovingemitter-zero-e)| | |
| |[ Fill](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#fill-zero-engine-documen)| | |
| |[ Lifetime](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#lifetime-zero-engine-doc)| | |
| |[ LifetimeVariance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#lifetimevariance-zero-en)| | |
| |[ RandomSpin](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#randomspin-zero-engine-d)| | |
| |[ RandomVelocity](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#randomvelocity-zero-engi)| | |
| |[ Size](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#size-zero-engine-documen)| | |
| |[ SizeVariance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#sizevariance-zero-engine)| | |
| |[ Spin](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#spin-zero-engine-documen)| | |
| |[ SpinVariance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#spinvariance-zero-engine)| | |
| |[ StartVelocity](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#startvelocity-zero-engin)| | |
| |[ TangentVelocity](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particleemittershared.markdown#tangentvelocity-zero-eng)| | |


 #  Properties


---  
 #  Active : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Is this emitter currently emitting particles?
> ``` lang=cpp, name=Zilch
> var Active : Boolean


---  
 #  EmitCount : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

> Number of particles to emit per reset.
> ``` lang=cpp, name=Zilch
> var EmitCount : Integer


---  
 #  EmitDelay : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> Time in seconds to delay the emission of particles from time of creation.
> ``` lang=cpp, name=Zilch
> var EmitDelay : Real


---  
 #  EmitRate : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> Rate that particles spawn per second.
> ``` lang=cpp, name=Zilch
> var EmitRate : Real


---  
 #  EmitRateSoftStartTime : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> Slowly ramps up to EmitRate over this time.
> ``` lang=cpp, name=Zilch
> var EmitRateSoftStartTime : Real


---  
 #  EmitterSize : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> Size of the emitter.
> ``` lang=cpp, name=Zilch
> var EmitterSize : Real3


---  
 #  EmitterVelocityPercent : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> How much of the objects velocity is added to the particles.
> ``` lang=cpp, name=Zilch
> var EmitterVelocityPercent : Real


---  
 #  EmitVariance : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> How much the emit can vary per sample.
> ``` lang=cpp, name=Zilch
> var EmitVariance : Real


---  
 #  FastMovingEmitter : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Whether or not we attempt to emit along the vector between the previous position to the current position, which looks better for fast moving particle systems Note: Particle systems that teleport will emit along the teleport line.
> ``` lang=cpp, name=Zilch
> var FastMovingEmitter : Boolean


---  
 #  Fill : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> How much area of the emitter to used 0 to 1.
> ``` lang=cpp, name=Zilch
> var Fill : Real


---  
 #  Lifetime : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> How a particle's starting lifetime is.
> ``` lang=cpp, name=Zilch
> var Lifetime : Real


---  
 #  LifetimeVariance : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> How much lifetime can vary per particle.
> ``` lang=cpp, name=Zilch
> var LifetimeVariance : Real


---  
 #  RandomSpin : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Each particle should start with random spin.
> ``` lang=cpp, name=Zilch
> var RandomSpin : Boolean


---  
 #  RandomVelocity : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> Random Velocity per particle.
> ``` lang=cpp, name=Zilch
> var RandomVelocity : Real3


---  
 #  Size : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> Size of each particle spawned.
> ``` lang=cpp, name=Zilch
> var Size : Real


---  
 #  SizeVariance : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> How much the size can vary from the base size per particle.
> ``` lang=cpp, name=Zilch
> var SizeVariance : Real


---  
 #  Spin : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> Speed in rads per second of the particle.
> ``` lang=cpp, name=Zilch
> var Spin : Real


---  
 #  SpinVariance : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> How much spin speed can vary per particle.
> ``` lang=cpp, name=Zilch
> var SpinVariance : Real


---  
 #  StartVelocity : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> Velocity of each particle at start.
> ``` lang=cpp, name=Zilch
> var StartVelocity : Real3


---  
 #  TangentVelocity : [real3](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real3.markdown)

> Velocity of each particle in x horizontal tangent y vertical tangent and z outward tangent.
> ``` lang=cpp, name=Zilch
> var TangentVelocity : Real3


---  
 #  Methods


---  
 #  ResetCount : Void

> Reset the number of particles to emit back to EmitCount.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ResetCount()
> ``` 


---  
 

 