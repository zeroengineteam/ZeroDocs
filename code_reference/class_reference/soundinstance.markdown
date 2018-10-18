 `Sound`

(NOTE) The object associated with a currently playing sound.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ InterpolateDecibels](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstance.markdown#interpolatedecibels-void)|[ CustomEventTime](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstance.markdown#customeventtime-zero-eng)|[referencecountedeventobject](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/referencecountedeventobject.markdown)| |
|[ InterpolatePitch](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstance.markdown#interpolatepitch-void)|[ Decibels](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstance.markdown#decibels-zero-engine-doc)| | |
|[ InterpolateSemitones](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstance.markdown#interpolatesemitones-voi)|[ EndTime](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstance.markdown#endtime-zero-engine-docu)| | |
|[ InterpolateVolume](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstance.markdown#interpolatevolume-void)|[ FileLength](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstance.markdown#filelength-zero-engine-d)| | |
|[ Stop](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstance.markdown#stop-void)|[ IsPlaying](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstance.markdown#isplaying-zero-engine-do)| | |
| |[ LoopEndTime](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstance.markdown#loopendtime-zero-engine)| | |
| |[ Looping](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstance.markdown#looping-zero-engine-docu)| | |
| |[ LoopStartTime](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstance.markdown#loopstarttime-zero-engin)| | |
| |[ Paused](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstance.markdown#paused-zero-engine-docum)| | |
| |[ Pitch](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstance.markdown#pitch-zero-engine-docume)| | |
| |[ Semitones](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstance.markdown#semitones-zero-engine-do)| | |
| |[ SoundName](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstance.markdown#soundname-zero-engine-do)| | |
| |[ SoundNode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstance.markdown#soundnode-zero-engine-do)| | |
| |[ Time](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstance.markdown#time-zero-engine-documen)| | |
| |[ Volume](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundinstance.markdown#volume-zero-engine-docum)| | |


 #  Properties


---  
 #  CustomEventTime : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The time (in seconds from the beginning of the file) to get a MusicCustomTime event.
> ``` lang=cpp, name=Zilch
> var CustomEventTime : Real


---  
 #  Decibels : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The volume adjustment (in decibels) of the SoundInstance, initially set by the SoundCue's Decibels property. A value of 0 does nothing, 6 will double the sound's volume, -6 will halve it. The Decibels property is linked to the Volume property (changing one will change the other).
> ``` lang=cpp, name=Zilch
> var Decibels : Real


---  
 #  EndTime : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The time in seconds from the beginning of the file that the instance will stop.
> ``` lang=cpp, name=Zilch
> var EndTime : Real


---  
 #  FileLength : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

 `read-only`

> The length of the entire audio file, in seconds.
> ``` lang=cpp, name=Zilch
> var FileLength : Real


---  
 #  IsPlaying : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> This Property will be true while the SoundInstance is playing, then will become false when its sound has stopped.
> ``` lang=cpp, name=Zilch
> var IsPlaying : Boolean


---  
 #  LoopEndTime : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The time in seconds from the beginning of the file that the instance will stop and jump back when looping.
> ``` lang=cpp, name=Zilch
> var LoopEndTime : Real


---  
 #  Looping : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> When this Property is true the SoundInstance will loop indefinitely. If changed to false while a SoundInstance is looping the SoundInstance will continue playing to its EndTime and then stop.
> ``` lang=cpp, name=Zilch
> var Looping : Boolean


---  
 #  LoopStartTime : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The time in seconds from the beginning of the file that the instance will jump back to when it loops.
> ``` lang=cpp, name=Zilch
> var LoopStartTime : Real


---  
 #  Paused : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Setting this Property to true will pause a currently playing SoundInstance. Setting it to false will resume playback.
> ``` lang=cpp, name=Zilch
> var Paused : Boolean


---  
 #  Pitch : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The pitch adjustment of the SoundInstance, initially set by the SoundCue's Pitch property. A value of 0 will do nothing, 1 will raise the pitch by an octave and speed up the sound,.
> ``` lang=cpp, name=Zilch
> var Pitch : Real


---  
 #  Semitones : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The pitch adjustment, in semitones (or half-steps), of the SoundInstance, initially set by the SoundCue's Semitones property. A value of 0 will do nothing, 12 will raise the pitch by an octave and speed up the sound, and -12 will lower the sound by an octave and slow it down. The Semitones property is linked to the Pitch property (changing one will change the other).
> ``` lang=cpp, name=Zilch
> var Semitones : Real


---  
 #  SoundName : [string](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown)

 `read-only`

> The name of the Sound being played by this SoundInstance.
> ``` lang=cpp, name=Zilch
> var SoundName : String


---  
 #  SoundNode : [soundnode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundnode.markdown)

 `read-only`

> The SoundNode associated with this SoundInstance.
> ``` lang=cpp, name=Zilch
> var SoundNode : SoundNode


---  
 #  Time : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> This property tells you to the current playback position, in seconds from the beginning of the file, and allows you to tell the instance to change its playback position to a different time. Be aware that the time will not be precisely accurate. If the Sound resource used to play the SoundInstance has Streamed selected, you cannot set the playback position.
> ``` lang=cpp, name=Zilch
> var Time : Real


---  
 #  Volume : [real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)

> The volume adjustment of the SoundInstance, initially set by the SoundCue's Volume property. A value of 1 does nothing, 2 will double the sound's volume, 0.5 will halve it. The Volume property is linked to the Decibels property (changing one will change the other).
> ``` lang=cpp, name=Zilch
> var Volume : Real


---  
 #  Methods


---  
 #  InterpolateDecibels : Void

> Interpolates the SoundInstance's Decibels property from its current value to the value passed in as the first parameter, over the number of seconds passed in as the second parameter.
> |Name|Type|Description|
> |---|---|---|
> |decibels|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |interpolationTime|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function InterpolateDecibels(decibels : Real, interpolationTime : Real)
> ``` 


---  
 #  InterpolatePitch : Void

> Interpolates the SoundInstance's Pitch property from its current value to the value passed in as the first parameter, over the number of seconds passed in as the second parameter.
> |Name|Type|Description|
> |---|---|---|
> |pitch|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |interpolationTime|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function InterpolatePitch(pitch : Real, interpolationTime : Real)
> ``` 


---  
 #  InterpolateSemitones : Void

> Interpolates the SoundInstance's Semitones property from its current value to the value passed in as the first parameter, over the number of seconds passed in as the second parameter.
> |Name|Type|Description|
> |---|---|---|
> |pitchSemitones|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |interpolationTime|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function InterpolateSemitones(pitchSemitones : Real, interpolationTime : Real)
> ``` 


---  
 #  InterpolateVolume : Void

> Interpolates the SoundInstance's Volume property from its current value to the value passed in as the first parameter, over the number of seconds passed in as the second parameter.
> |Name|Type|Description|
> |---|---|---|
> |volume|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> |interpolationTime|[real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function InterpolateVolume(volume : Real, interpolationTime : Real)
> ``` 


---  
 #  Stop : Void

> Stops the playback of this SoundInstance. It cannot be re-started.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Stop()
> ``` 


---  
 

 