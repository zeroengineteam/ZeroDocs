The particle animator uses [ColorGradients](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/architecture/resources/colorgradient.markdown) to color each particle uniquely based on its current state.  The final color of any given particle is calculated from an element-wise multiplication of three color vectors:
```Color = VertexColor * TimeGradientColor * VelocityGradientColor```
where `VertexColor` comes from VectexColor  on the [SpriteParticleSystem](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/code_reference/class_reference/spriteparticlesystem.markdown) component.  `TimeGradientColor` is then found from sampling the TimeGradient resource, while `VelocityGradientColor` is found from sampling the VelocityGradient resource.



![ParticleSystems_ColorGradients](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46668.gif) *The TimeGradient resource is interpolated from black to white to black such that the color fades in and out.  The VelocityGradient resource is interpolated from blue to red, such that slow particles are blue and fast particles are red.*


 # Time and Velocity Gradients
In order to use the gradients on the `ParticleColorAnimator`, one must understand how each gradient is sampled. The TimeGradient resource defines colors in the range of `t[0,1]`.  When `t=0`, the particle is created, and when `t=1`, the particle dies.  The range is important because we need to map time that the particle has lived to `[0,1]`.  When sampling from TimeGradient resource, the `ParticleColorAnimator` uses the particle lifetime as the range.

When sampling from VelocityGradient resource, the magnitude of the velocity is used.  However, unlike with time, `ParticleColorAnimator` can't guess how to map velocity magnitudes to the `[0,1]` range.  `ParticleColorAnimator` therefore includes MaxParticleSpeed  as an upper limit.  When `t=0` the particle isn't moving, and when `t=1` when the particle is moving at the speed of MaxParticleSpeed .

 # Related Material
 ## Manual
- [Color Gradient](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/architecture/resources/colorgradient.markdown)
- [Sprite Particle System](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/tutorials/graphics/particles/sprite_particle_system.markdown)

 ## Code Reference
- [SpriteParticleSystem](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/code_reference/class_reference/spriteparticlesystem.markdown) 
  
  
  
  
  
  
  

 