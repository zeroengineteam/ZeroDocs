The [ SoundEmitter ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown) component handles the 3D positioning of sounds in a level. For instance, if the SoundEmitter's object is to the left of a [SoundListener ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundlistener.markdown), it will reduce the amount of sound going to the right speaker, so that the player hears the sound to their left. 

 # Using SoundEmitters


![SoundEmitter1](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47924.png)


 ## Volume and Pitch Settings

The Volume  and Decibels  properties set the volume adjustment that is applied to any [SoundInstances](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundinstance.markdown) played through the SoundEmitter. The Volume  property uses floating point values, while the Decibels  property uses the logarithmic decibel scale commonly used in audio. These properties are linked, so changing one will also change the value of the other. 

The Pitch  and Semitones  properties set the pitch adjustment that is applied to SoundInstances. This adjustment affects both the pitch and speed of the sound: higher-pitched sounds will play faster, while lower-pitched sounds play slower. Large pitch changes will likely affect the quality of the sound. The Pitch  property uses floating point values, while the Semitones  property uses semitones, or half-steps. These properties are also linked.

The `InterpolateVolume`, `InterpolateDecibels`, `InterpolatePitch`, and `InterpolateSemitones` methods can be used at runtime to smoothly change the SoundEmitter's volume or pitch over time. Using these interpolation methods is preferable to using Actions to set the properties: changing a property every frame with an Action can result in audible jumps in volume or pitch, while the interpolation method causes the volume change to be handled smoothly by the audio engine.

Note that these volume and pitch changes will be combined with any other volume modifications applied by objects such as [SoundTags](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundtag.markdown), [SoundCues](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundcue.markdown), and [SoundSpaces](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundspace.markdown). If a SoundCue's volume is set to `0.5` and it is played on a SoundEmitter which also has a volume of `0.5`, this effectively sets the resulting SoundInstance's volume to `0.25`. If a SoundInstance's Semitones is set to `12` and it is played on a SoundEmitter with a Semitones value of `-6`, this effectively raises the SoundInstance's pitch by 6 semitones or half an octave. 

 ## Directional SoundEmitters



![SoundEmitter2](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47926.png) When the Directional checkBox property is checked the audio output of the SoundEmitter will be limited by the EmitAngle  so that sound in front of the object will be louder than sound behind it. Within the EmitAngle   the sound will be at full volume. Outside the angle, the volume will interpolate using a logarithmic curve until it reaches the RearVolume  value directly behind the object. This is useful for sounds on objects such as loudspeakers or objects with a wall behind them that the sound shouldn't be heard through.


 ## Attenuation

If a [SoundAttenuator](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundattenuator.markdown) resource other than DefaultNoAttenuation resource is selected, its settings will be used for any SoundCues played through the SoundEmitter that have DefaultNoAttenuation resource selected on their Attenuator resource property. 

 ## SoundNodes

Unlike other objects, SoundEmitters are a collection of multiple [SoundNodes ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundnode.markdown). This allows them to have settings for volume and pitch as well as handling spatialization. Because of this, instead of one SoundNode property, SoundEmitters have two separate properties for the first and last SoundNodes in their chain. 

The `InputNode` property should be used for attaching other SoundNodes to the input of the SoundEmitter, while the `OutputNode` should be used for attaching to its output. Users cannot insert other SoundNodes before or after the `InputNode`, and cannot insert SoundNodes before the `OutputNode`. Neither of these nodes can be replaced or removed from the graph.

 ##  Zilch Events

- The `SoundInstancePlayed` [ SoundInstanceEvent  ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundinstanceevent.markdown) will be sent when a SoundCue is played using either the `PlayCue` or `PlayCuePaused` methods. 
- The `AudioInterpolationDone` [ SoundEvent  ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundevent.markdown) is sent whenever a volume or pitch interpolation has finished.

---
 # Related Materials

 ## Manual

- [SoundListener ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundlistener.markdown)
- [SoundInstance ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundinstance.markdown)
- [SoundTag ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundtag.markdown)
- [SoundCue ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundcue.markdown)
- [SoundSpace ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundspace.markdown)
- [SoundAttenuator ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundattenuator.markdown)
- [SoundNode ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundnode.markdown)

 ## Reference

- [ SoundEmitter ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown)
- [ SoundInstanceEvent  ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundinstanceevent.markdown) 
- [ SoundEvent  ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundevent.markdown)  

 