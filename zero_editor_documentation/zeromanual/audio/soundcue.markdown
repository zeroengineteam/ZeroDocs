[ SoundCues ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundcue.markdown) are a fundamental part of playing audio in the Zero Engine. However the user chooses to play a sound, they will need to use a SoundCue to play it. SoundCues allow the user to modify various properties without affecting the original [Sound ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/sound.markdown) resource: the same Sound can be applied to different SoundCues, have different property values on the SoundCue, and end up sounding completely different. 

 # Common Uses

- Playing sounds with a [SimpleSound ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/simplesound.markdown) component
- Playing sounds at runtime using methods on [SoundEmitters ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundemitter.markdown) or [SoundSpaces ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundspace.markdown)
- Playing sounds directly on a [SoundNode ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundnode.markdown)

 # Using SoundCues



![SoundCue1](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47918.png)

If a SoundCue has multiple Sounds attached it can either randomly select which Sound to use each time it is played or it can play them sequentially. Each time a SoundCue is played it creates a new [SoundInstance ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundinstance.markdown), which can then be accessed in ZilchScripts to control the sound as it's playing. Changing properties on the SoundInstance does not affect the properties on the SoundCue.

 ## Volume Settings

The Volume  and  Decibels  properties set the volume adjustment that is applied to a sound when the SoundCue is played. The Volume  property uses floating point values, while the Decibels  property uses the logarithmic decibel scale commonly used in audio. These properties are linked, so changing one will also change the value of the other.

If UseDecibelVariation checkBox is checked, the DecibelVariation  property will be shown in the Property Window and will be used when randomizing the volume of a new SoundInstance. If not checked, the VolumeVariation  property will be shown and used for randomization. These properties set how much the volume of SoundInstances will be randomized each time the SoundCue plays. For instance, if the Volume  value is `1` and VolumeVariation  is `0.5` the volume of the SoundInstance will be chosen randomly from between `0.5` and `1.5`. 

Note that these volume changes will be multiplied together with any other volume modifications applied by objects such as [SoundTags ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundtag.markdown), SoundEmitters, and SoundSpaces. If a SoundCue's volume is set to `0.5` and it is played on a SoundEmitter which also has a volume of `0.5`, this effectively sets the resulting SoundInstance's volume to `0.25`.

 ## Pitch Settings

The  Pitch  and  Semitones  properties set the pitch adjustment that is applied to the SoundInstance whenever the SoundCue is played. This adjustment affects both the pitch and speed of the sound: higher-pitched sounds will play faster, while lower-pitched sounds play slower. Large pitch changes will likely affect the quality of the sound. The  Pitch  property uses floating point values, while the Semitones  property uses semitones, or half-steps. These properties are linked, so changing one will also change the value of the other.

If UseSemitoneVariation checkBox is checked, the  SemitoneVariation  property will be shown in the Property Window and will be used when randomizing the pitch of a new SoundInstance. If not checked, the  PitchVariation  property will be shown and used for randomization. These properties set how much the pitch of SoundInstances will be randomized every time the SoundCue plays. For instance, if the  Pitch  value is `0` and  PitchVariation  is `0.3` the pitch of the SoundInstance will be chosen randomly from between `-0.3` and `0.3`.

Note that these changes will be combined with any other pitch modifications applied by objects such as SoundEmitters and SoundSpaces. If a SoundInstance's  Semitones  is set to `12` and it is played on a SoundEmitter with a  Semitones  value of `-6`, this effectively raises the SoundInstance's pitch by 6 semitones.

 ## Attenuation

If a [SoundAttenuator ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundattenuator.markdown) resource other than `DefaultNoAttenuation` is selected its settings will be used when the SoundCue is played on a SoundEmitter to change the sound's volume depending on the distance to a [SoundListener ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundlistener.markdown). Otherwise, either the attenuation settings on the SoundEmitter will be used, or if the SoundEmitter has no settings, the sound will not be attenuated.

 ## Music Notification Settings 



![SoundCue2](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47920.png) 

If the ShowMusicOptions checkBox box is checked, fields will be shown for setting the speed and time signature of a music file. The two numbers in the time signature tell how many beats are in each measure of music and what type of note has the beat. For instance, a time signature of 4/4 has four quarter note beats per measure, and 3/8 has three eighth note beats. 

If all three of the fields are set to values other than zero, whenever the SoundCue is played the resulting SoundInstance will send Zilch events for every bar, beat, whole note, half note, quarter note, and eighth note (see the [SoundInstance ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundinstance.markdown) page for more details). 

 ## SoundEntries 



![SoundEntry](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47922.png)

Each [ SoundEntry ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundentry.markdown) holds a Sound which can be played by the SoundCue. SoundEntries have properties to control when the audio file starts and stops, when it starts looping and stops looping, and whether it should cross-fade audio after it loops.

 ## SoundTagEntries

Every [ SoundTag ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundtag.markdown) in the list of SoundTagEntries will be applied to the resulting SoundInstance whenever a SoundCue is played. SoundTags allow the user to control SoundInstances as a group. See the [SoundTag ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundtag.markdown) page for more information.

 ##  Zilch Events

- The `SoundCuePrePlay` [ SoundInstanceEvent  ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstanceevent.markdown) is sent just before a SoundInstance is played. 
- The `SoundCuePostPlay` SoundInstanceEvent is sent immediately afterward. 

The following code block shows how to connect to the `SoundCuePrePlay` event and change the SoundInstance's volume before it plays.

```lang=csharp
[Property] var Cue : SoundCue;

function Initialize(init : CogInitializer)
{
  Zero.Connect(this.Cue, Events.SoundCuePrePlay, this.OnCuePlay);
}

function OnCuePlay(event : SoundInstanceEvent)
{
  event.SoundInstance.Volume = 0.5;
}
```

---
 # Related Materials

 ## Manual

- [Sound ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/sound.markdown)
- [SimpleSound ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/simplesound.markdown)
- [SoundEmitter ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundemitter.markdown)
- [SoundSpace ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundspace.markdown)
- [SoundNode ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundnode.markdown)
- [SoundInstance ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundinstance.markdown)
- [SoundTag ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundtag.markdown)
- [SoundAttenuator ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundattenuator.markdown)
- [SoundListener ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundlistener.markdown)

 ## Reference

- [ SoundCue ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundcue.markdown)
- [ SoundEntry ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundentry.markdown)
- [ SoundTag ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundtag.markdown)
- [ SoundInstanceEvent ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstanceevent.markdown) 

 