Emitters are necessary components for a particle system that define the properties of a particle as it's created.  One of those properties is the spawn position, which is in part defined by the component itself.  The emitter types are [BoxParticleEmitter](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/boxparticleemitter.markdown), [SphericalParticleEmitter](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/sphericalparticleemitter.markdown), and [MeshParticleEmitter](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/meshparticleemitter.markdown), and each one defines a surface or curve that particles emit from.



![ParticleSystems_MeshEmitter](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46683.gif) *Cycling through meshes on a `MeshParticleEmitter`*


NOTE: By default the shape isn't apparent on the Box or Sphere particle emitter.  This is because the EmitterSize  is zeroed out by default.

 # Variance
Some properties on an emitter have a variance property to match.  Each particle inherits its properties from the emitter by adding a random value from variance to base value.  For example, two common properties for emitters are Size  and SizeVariance .  If Size  were set to `1` and the SizeVariance  was `0.1`, the size of each particle would be a random value in the range `[0.9,1.1]`.  The property StartVelocity  also has the variance counterpart RandomVelocity .  The velocity vector is computed similarly with a variance property, where the X, Y, and Z components of the vector are computed independently.

 # Fast Emitters
When an object is moving fast, the fact that its motion is an illusion becomes more apparent.  When the gaps between the small teleportations grow bigger, the illusion is lost.  The illusion of motion is even harder to keep when a particle system is moving since the particles tend to trace the path of the object.  One way to fix this is to use a high EmitRate  and turn on FastMovingEmitter checkBox.  This will emit some of the extra particles between the gaps of the current and previous positions.



![ParticleSystems_FastMovingEmitter](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46688.gif) *Two particle emitters in motion, where the right one is using FastMovingEmitter checkBox*


 # Related Material
 ## Manual
- [Color Gradient](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/architecture/resources/colorgradient.markdown)

 ## Code Reference
- [SpriteParticleSystem](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/code_reference/class_reference/spriteparticlesystem.markdown)
- [BoxParticleEmitter](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/boxparticleemitter.markdown)
- [SphericalParticleEmitter](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/sphericalparticleemitter.markdown)
- [MeshParticleEmitter](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/meshparticleemitter.markdown)
 

 