The [ SoundSpace ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundspace.markdown) is one of the default components of a Space. Its basic purpose is to separate sound areas, which means that a [SoundListener](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundlistener.markdown) in one SoundSpace can’t hear sounds in a different SoundSpace. It also allows the user to control properties like pitch and volume for all sounds in the Space. 

 # Using SoundSpaces

 ## Playing SoundCues

[SoundCues  ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundcue.markdown) can be played through SoundSpaces for non-positional audio that does not go through the SoundListeners. The `PlayCue` method will start playing the SoundCue immediately, while the `PlayCuePaused` method will create a paused [SoundInstance ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundinstance.markdown), which allows the user to change its settings before un-pausing it.

```lang=csharp
this.MySoundInstance = this.Space.SoundSpace.PlayCuePaused(this.MySoundCue);
this.MySoundInstance.Volume = 0.5;
this.MySoundInstance.Paused = false;
```

 ## Controlling Volume and Pitch

The Volume  and Decibels  properties set the volume adjustment applied to all sound in the SoundSpace. Volume  uses floating point values, while Decibels  uses the logarithmic decibel scale commonly used in audio. These properties are linked, so changing one will also change the value of the other.

The Pitch  and Semitones  properties set the pitch adjustment applied to all sounds. This adjustment affects both the pitch and speed of the sound: higher-pitched sounds will play faster, while lower-pitched sounds play slower. Large pitch changes will likely affect the quality of the sound. Pitch  uses floating point values, while Semitones  uses semitones, or half-steps. These properties are also linked.

The `InterpolateVolume`, `InterpolateDecibels`, `InterpolatePitch`, and `InterpolateSemitones` methods can be used at runtime to smoothly change the SoundSpace's volume or pitch over time. Using these interpolation methods is preferable to using Actions to set the properties: changing a property every frame with an Action can result in audible jumps in volume or pitch, while the interpolation method causes the volume change to be handled smoothly by the audio engine.

Note that these volume changes will be combined with any other volume modifications applied by objects such as [SoundTags](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundtag.markdown), [SoundEmitters](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundemitter.markdown), and SoundCues. If a SoundCue's {Volume  is set to `0.5` and it is played on a SoundSpace which also has a volume of `0.5`, this effectively sets the SoundInstance's volume to `0.25`. If the SoundCue's Semitones  is set to `12` and it is played on a SoundSpace with a Semitones  value of `-6`, this effectively raises the SoundInstance's pitch by half an octave.

When the PitchWithTimeSpace checkBox property is `true`, which is the default, the audio of the SoundSpace will be pitched according to the `TimeScale` of the Space. In other words, if time slows down the audio will slow down and lower in pitch, and if time is sped up the audio will speed up and raise in pitch.

 ## Controlling Playback

SoundSpaces can be paused by setting their Paused checkBox property to `true`. This will stop all audio processing for SoundInstances in that SoundSpace. When the Paused checkBox property is set to `false` the SoundInstances will resume playing with no changes. 

If the `icon-check-square-o, name=PauseWithTimeSpace` property is `true`, which is the default, the SoundSpace will be paused when the Space is paused.

 ## SoundNodes

Each SoundSpace has a single [SoundNode ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundnode.markdown) that all audio in the Space is connected to, the `InputNode`. SoundListeners are connected directly to this node, as well as SoundInstances that are not played through a SoundEmitter. Since the SoundSpace uses additional SoundNodes to modify pitch and volume, it also has an `OutputNode` property which you can use to attach to the output of the SoundSpace. SoundNodes that the user creates to affect all audio in the SoundSpace should be inserted after the `OutputNode`. 

NOTE: SoundNodes that are inserted after the SoundSpace's `OutputNode` must be removed by the user, as these will not be automatically removed when the SoundSpace is destroyed.

SoundNodes cannot be inserted after the `InputNode` or before the `OutputNode`, and neither of these nodes can be replaced or removed from the graph.

---
 #  Related Materials

 ## Manual

- [SoundListener ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundlistener.markdown)
- [SoundCue ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundcue.markdown)
- [SoundInstance ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundinstance.markdown)
- [SoundTag ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundtag.markdown)
- [SoundEmitter ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundemitter.markdown)
- [SoundNode ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundnode.markdown)

 ## Reference

- [ SoundSpace ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundspace.markdown) 

 