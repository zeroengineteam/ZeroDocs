The [SpriteParticleSystem](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/spriteparticlesystem.markdown) is a [graphical](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/graphical.markdown) and a necessary component of a particle system.  Particle systems not only provide a simple interface for applying visual effects to an object, but are more efficient than spawning the equivalent [game objects](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/architecture/cogs/gameobjectsconcept.markdown) under the same conditions.  When editing particle systems, it is important to note that no one particle has unqiue logic in the same system. Every particle follows the same set of universal rules within the system to transform how they are rendered.

 # BoundingBoxSize
Some objects have a bounding box to determine if they should be rendered or not.  Either all particles in a particle system are renderered, or none of them are.  It's up to the user to determine how far off the screen is far enough to stop rendering any given system.  The BoundingBoxSize  defines the width, length, and height of the bounding box.  Once the bounding box leaves the screen, the particle system won't render.



![ParticleSystems_BoundingBoxSize](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47864.gif)


WARNING:  Be careful of particles that leave the bounding box, because these are the particles that have potential to disappear.

 # Particle System Hierarchies
When working with particle system hierarchies, the ChildSystem checkBox switch gives the ability to make a particle system of particle systems.  This means that a child particle system will emit particles on each particle of a parent particle system.  To force a particle system to generate particles in this way, ChildSystem checkBox should be checked.



![ParticleSystems_ChildSystem](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46652.gif)


 # Particle Spaces
The [SystemSpace](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#systemspace) is used to set the space for particles in the particle system.  If SystemSpace enum is set to **WorldSpace**, then particles are created in world space and position is not longer affected by the `Transform` component.  If SystemSpace enum is set to **LocalSpace**, then the space is the Transform, and will therefore follow the Transform.



![ParticleSystems_SystemSpace](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47862.gif)


 # Geometry Mode
Particles made in the Sprite Particle System are 2D, so the way that particles are placed in a 3D environment needs to be determined.  The [GeometryMode](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#spriteparticlegeometrymode) parameter has the following modes:
| Mode | Description |
| -- | -- |
| `Billboarded` | Each particle faces the camera |
| `Beam` | Same as `Billboarded`, but each particle is stretched by its velocity vector |
| `Outward` | Each particle faces the particle system origin |
| `Face Velocity | Each particle faces the direction of its velocity vector |
| `Flat` | Each particle faces the SystemSpace enum Z-axis |



![ParticleSystems_GeometryMode](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46660.gif)


---

 # Related Material
 ## Reference
- [SpriteParticleSystem](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/spriteparticlesystem.markdown)
- [graphical](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/graphical.markdown)
- [LinearParticleAnimator](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/linearparticleanimator.markdown) 

 