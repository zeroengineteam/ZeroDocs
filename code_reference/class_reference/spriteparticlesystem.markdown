 `Component` `Graphics`



(NOTE) A particle system that uses sprites to represent each particle.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/spriteparticlesystem.markdown#spriteparticlesystem-voi)|[ BeamBaseScale](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/spriteparticlesystem.markdown#beambasescale-zero-engin)|[particlesystem](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/particlesystem.markdown)| |
| |[ BeamVelocityScale](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/spriteparticlesystem.markdown#beamvelocityscale-zero-e)| | |
| |[ GeometryMode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/spriteparticlesystem.markdown#geometrymode-zero-engine)| | |
| |[ ParticleAnimation](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/spriteparticlesystem.markdown#particleanimation-zero-e)| | |
| |[ ParticleSort](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/spriteparticlesystem.markdown#particlesort-zero-engine)| | |
| |[ SpriteSource](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/spriteparticlesystem.markdown#spritesource-zero-engine)| | |
| |[ VertexColor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/spriteparticlesystem.markdown#vertexcolor-zero-engine)| | |


 #  Properties


---  
 #  BeamBaseScale : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> How much to scale particles along their direction of movement.
> ``` lang=cpp, name=Zilch
> var BeamBaseScale : Real


---  
 #  BeamVelocityScale : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> How much additional scale to add to particles by how fast they are moving.
> ``` lang=cpp, name=Zilch
> var BeamVelocityScale : Real


---  
 #  GeometryMode : [SpriteParticleGeometryMode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#spriteparticlegeometrymode)

> How the geometry of the particles are generated.
> ``` lang=cpp, name=Zilch
> var GeometryMode : SpriteParticleGeometryMode


---  
 #  ParticleAnimation : [SpriteParticleAnimationMode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#spriteparticleanimationmode)

> How the sprite's animation should be used.
> ``` lang=cpp, name=Zilch
> var ParticleAnimation : SpriteParticleAnimationMode


---  
 #  ParticleSort : [SpriteParticleSortMode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#spriteparticlesortmode)

> How particles should be sorted with each other, determines draw order between particles.
> ``` lang=cpp, name=Zilch
> var ParticleSort : SpriteParticleSortMode


---  
 #  SpriteSource : [spritesource](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/spritesource.markdown)

> The sprite definition to use for each particle.
> ``` lang=cpp, name=Zilch
> var SpriteSource : SpriteSource


---  
 #  VertexColor : [real4](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real4.markdown)

> Color attribute of the generated vertices accessible in the vertex shader, value is multiplied with the particle color.
> ``` lang=cpp, name=Zilch
> var VertexColor : Real4


---  
 #  Methods


---  
 #  SpriteParticleSystem : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function SpriteParticleSystem()
> ``` 


---  
 
  
  
  
  
  
  
  

 