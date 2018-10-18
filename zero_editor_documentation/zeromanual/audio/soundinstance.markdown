[ SoundInstances ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundinstance.markdown) are created at runtime whenever a [SoundCue](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundcue.markdown) is played. Their properties are initially set by the SoundCue, but the user can then manipulate the SoundInstance's properties without affecting the SoundCue or any other SoundInstances created by it. 

 #  Using SoundInstances

A SoundInstance is returned by the `PlayCue`and `PlayCuePaused` methods on [SoundEmitters ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundemitter.markdown) and [SoundSpaces ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundspace.markdown), the `Play` method on [SimpleSounds ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/simplesound.markdown), and the `PlayCueOnNode` method on SoundCues. If a `PlayCuePaused` method is used, the SoundInstance must have its Paused checkBox property set to `False` before it will begin playing.

SoundInstance objects are reference counted: they will stay alive as long as a variable is stored with the SoundInstance assigned to it, so the SoundInstance can still be accessed even after it finishes playing. If the user does not store a variable, the SoundInstance will continue playing audio, but cannot be accessed in ZilchScripts.

 ## Controlling Playback

When a SoundInstance is paused it stops playing all audio, then can be resumed and will continue playing where it left off, with no change to its settings or behavior. SoundInstances have a single Boolean property, Paused checkBox, which controls whether they are playing or paused. If Paused checkBox is set to `true` when the SoundInstance is already paused, or set to `false` when it is not paused, nothing will happen.

When a SoundInstance is stopped using the `Stop` method it immediately stops playing audio and cannot be restarted.

The  Time  property tells the user the current playback position of a SoundInstance, in seconds, from the beginning of the audio file used for the sound. It also allows the user to tell the SoundInstance to jump to a different position. Note that when reading the  Time  property, the time given will not be precisely accurate. It will never be ahead of the exact position, but, due to the multi-threaded nature of the audio system, it may be very slightly behind.

 ## Controlling Volume and Pitch

The Volume  and Decibels  properties set the volume adjustment that is applied to the SoundInstance. Volume  uses floating point values, while  Decibels  uses the logarithmic decibel scale commonly used in audio. These properties are linked, so changing one will also change the value of the other.

The  Pitch  and  Semitones  properties set the pitch adjustment that is applied to the SoundInstance. This adjustment affects both the pitch and speed of the sound: higher-pitched sounds will play faster, while lower-pitched sounds play slower. Large pitch changes will likely affect the quality of the sound.  Pitch  uses floating point values, while the  Semitones  uses semitones, or half-steps. These properties are also linked.

The `InterpolateVolume`, `InterpolateDecibels`, `InterpolatePitch`, and `InterpolateSemitones` methods can be used at runtime to smoothly change the SoundInstance's volume or pitch over time. Using these interpolation methods is preferable to using Actions to set the properties: changing a property every frame with an Action can result in audible jumps in volume or pitch, while the interpolation method causes the volume change to be handled smoothly by the audio engine.

Note that these volume changes will be combined with any other volume modifications applied by objects such as [SoundTags ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundtag.markdown), SoundEmitters, and SoundSpaces. If a SoundInstance's  Volume  is set to `0.5` and it is played on a SoundEmitter which also has a  Volume  of `0.5`, this effectively sets the SoundInstance's  Volume  to `0.25`. If it's  Semitones  is set to `12` and it is played on a SoundEmitter with a  Semitones  value of `-6`, this effectively raises the SoundInstance's pitch by half an octave.

 ## Looping

A SoundInstance's  Looping checkBox property is initially set by the corresponding property on the SoundCue. When this property is `true`, the SoundInstance will repeat indefinitely, using the  LoopStartTime  and  LoopEndTime  properties on the [SoundEntry](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundcue.markdown#soundentry) that the SoundCue used to create the SoundInstance. If a SoundInstance is looping and the property is changed to `false` as it is playing it will continue playing to its  EndTime  and then stop.

The following code block shows you how to make a SoundInstance finish naturally after it has looped three times, using the `SoundLooped` event.
```lang=csharp
// A property to be set to the SoundCue desired
[Property] var MySoundCue : SoundCue;

// A variable that will later be set to an instance of MySoundCue
var MySoundInstance : SoundInstance;
// A variable that will count how many times MySoundInstance has looped
var Counter : Integer = 0;

function Initialize(init : CogInitializer)
{
    // Create a SoundInstance by playing MySoundCue on the object's SoundSpace
    this.MySoundInstance = this.Space.SoundSpace.PlayCue(this.MySoundCue);
    // Connect to the SoundLooped event that will be sent by MySoundInstance
    Zero.Connect(this.MySoundInstance, Events.SoundLooped, this.OnSoundLoop);
}

function OnSoundLoop(event : SoundInstanceEvent)
{
    // Increase the counter
    ++this.Counter;
	
    if (this.Counter == 3)
    {
        // Tell the SoundInstance to stop looping, play until it reaches its end, and stop
        this.MySoundInstance.Looping = false;
    }
}
```

 ## Events

The following [ SoundInstanceEvents ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundinstanceevent.markdown) will be sent out by all SoundInstance objects:

- `SoundLooped` is sent by looping SoundInstances each time they reach their LoopEndTime  and jump back to their LoopStartTime .
- `SoundStopped` is sent when a SoundInstance has completely finished playing audio.
- `AudioInterpolationDone` will be sent whenever a volume or pitch interpolation has finished.

 ## Music Events

If the music options were set on the SoundCue before the SoundInstance was created (all three of the  BeatsPerMinute ,  TimeSigBeats , and  TimeSigValue  properties must be set) then the SoundInstance will also send the following SoundInstanceEvents:

- `MusicBeat` is sent on every beat of the music (the beat value set in the time signature).
- `MusicBar` is sent at the beginning of every measure.
- `MusicEighthNote` is sent for every eighth note beat of the music. (If the music's time signature is 4/4, you will receive eight `MusicEighthNote` events during every measure.) 
- `MusicQuarterNote` is sent for every quarter note beat of the music. (If the music's time signature is 4/4, you will receive four `MusicQuarterNote` events during every measure.)
- `MusicHalfNote` is sent for every half note beat of the music. (If the music's time signature is 4/4, you will receive two `MusicHalfNote` events during every measure.)
- `MusicWholeNote` is sent for every whole note beat of the music. (If the music's time signature is 4/4, you will receive one `MusicWholeNote` event for every measure.)

If the  CustomEventTime checkBox property is set, the SoundInstance will also send the `MusicCustomTime` event when it reaches that many seconds from the beginning of the audio file.

---
 # Related Materials

 ## Manual

- [SoundCue ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundcue.markdown)
- [SoundEmitter ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundemitter.markdown)
- [SoundSpace ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundspace.markdown)
- [SimpleSound ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/simplesound.markdown)
- [SoundTag ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundtag.markdown)

 ## Reference

- [ SoundInstance ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundinstance.markdown)
- [ SoundInstanceEvents ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundinstanceevent.markdown)  

 