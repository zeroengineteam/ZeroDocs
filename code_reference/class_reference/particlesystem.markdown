 `Component` `Graphics`



(NOTE) An interface for generating and managing particles of a generic definition using emitters and animators.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ AllParticles](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particlesystem.markdown#allparticles-zero-engine)|[ BoundingBoxSize](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particlesystem.markdown#boundingboxsize-zero-eng)|[graphical](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/graphical.markdown)|[spriteparticlesystem](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spriteparticlesystem.markdown)|
|[ Clear](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particlesystem.markdown#clear-void)|[ ChildSystem](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particlesystem.markdown#childsystem-zero-engine)| | |
| |[ PreviewInEditor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particlesystem.markdown#previewineditor-zero-eng)| | |
| |[ SystemSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particlesystem.markdown#systemspace-zero-engine)| | |
| |[ WarmUpTime](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particlesystem.markdown#warmuptime-zero-engine-d)| | |


 #  Properties


---  
 #  BoundingBoxSize : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> Size of all sides of the bounding box used for frustum culling.
> ``` lang=cpp, name=Zilch
> var BoundingBoxSize : Real


---  
 #  ChildSystem : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> If set, particle emission will happen for each particle in a parent system.
> ``` lang=cpp, name=Zilch
> var ChildSystem : Boolean


---  
 #  PreviewInEditor : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> If the particle system should run on frame update in the editor instead of logic update.
> ``` lang=cpp, name=Zilch
> var PreviewInEditor : Boolean


---  
 #  SystemSpace : [SystemSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#systemspace)

> If particles are emitted into world space or if transform data remains relative to the transform of the system object.
> ``` lang=cpp, name=Zilch
> var SystemSpace : SystemSpace


---  
 #  WarmUpTime : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The amount of time to simulate the particle system on startup. This will be done on AllObjectsCreated, and will use the engines dt. This is good for when you want the particle effect to be in full bloom when you first see it. However, it can hurt performance at high values on startup.
> ``` lang=cpp, name=Zilch
> var WarmUpTime : Real


---  
 #  Methods


---  
 #  AllParticles : [particlelistrange](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/particlelistrange.markdown)

> A list of all particles currently active in the system.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function AllParticles() : ParticleListRange
> ``` 


---  
 #  Clear : Void

> Clear all current particles.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Clear()
> ``` 


---  
 

 