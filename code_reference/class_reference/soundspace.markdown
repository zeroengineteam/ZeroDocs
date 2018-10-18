 `Component` `Sound`



(NOTE) Sound functionality associated with a Space.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ InterpolateDecibels](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundspace.markdown#interpolatedecibels-void)|[ Decibels](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundspace.markdown#decibels-zero-engine-doc)|[component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/component.markdown)| |
|[ InterpolatePitch](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundspace.markdown#interpolatepitch-void)|[ InputNode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundspace.markdown#inputnode-zero-engine-do)| | |
|[ InterpolateSemitones](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundspace.markdown#interpolatesemitones-voi)|[ MuteAudio](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundspace.markdown#muteaudio-zero-engine-do)| | |
|[ InterpolateVolume](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundspace.markdown#interpolatevolume-void)|[ OutputNode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundspace.markdown#outputnode-zero-engine-d)| | |
|[ PlayCue](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundspace.markdown#playcue-zero-engine-docu)|[ Paused](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundspace.markdown#paused-zero-engine-docum)| | |
|[ PlayCuePaused](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundspace.markdown#playcuepaused-zero-engin)|[ PauseWithTimeSpace](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundspace.markdown#pausewithtimespace-zero)| | |
|[ Constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundspace.markdown#soundspace-void)|[ Pitch](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundspace.markdown#pitch-zero-engine-docume)| | |
| |[ PitchWithTimeSpace](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundspace.markdown#pitchwithtimespace-zero)| | |
| |[ Semitones](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundspace.markdown#semitones-zero-engine-do)| | |
| |[ SoundNodeInput](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundspace.markdown#soundnodeinput-zero-engi)| | |
| |[ SoundNodeOutput](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundspace.markdown#soundnodeoutput-zero-eng)| | |
| |[ Volume](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundspace.markdown#volume-zero-engine-docum)| | |


 #  Properties


---  
 #  Decibels : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The volume adjustment, in decibels, applied to all sounds in the space. A value of 0 does nothing, 6 will double the sound's volume, -6 will halve it.
> ``` lang=cpp, name=Zilch
> var Decibels : Real


---  
 #  InputNode : [soundnode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundnode.markdown)

 `read-only`

> DEPRECATED The SoundNodeInput property should be used instead.
> ``` lang=cpp, name=Zilch
> var InputNode : SoundNode


---  
 #  MuteAudio : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Silences all audio output from this space but processes audio normally.
> ``` lang=cpp, name=Zilch
> var MuteAudio : Boolean


---  
 #  OutputNode : [soundnode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundnode.markdown)

 `read-only`

> DEPRECATED The SoundNodeOutput property should be used instead.
> ``` lang=cpp, name=Zilch
> var OutputNode : SoundNode


---  
 #  Paused : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Setting this Property to true will pause all audio in the space. Setting it to false will resume all audio.
> ``` lang=cpp, name=Zilch
> var Paused : Boolean


---  
 #  PauseWithTimeSpace : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> If true, the audio of the space will pause when the space is paused.
> ``` lang=cpp, name=Zilch
> var PauseWithTimeSpace : Boolean


---  
 #  Pitch : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The pitch adjustment applied to all sounds in the space. A value of 0 will do nothing, 1 will raise the pitch by an octave and speed up the sound, -1 will lower the sound by an octave and slow it down.
> ``` lang=cpp, name=Zilch
> var Pitch : Real


---  
 #  PitchWithTimeSpace : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> If true, the audio in the SoundSpace will be pitched according to the TimeScale of the Space(if time slows down the audio will slow down and lower in pitch, if it speeds up the audio will speed up and raise in pitch).
> ``` lang=cpp, name=Zilch
> var PitchWithTimeSpace : Boolean


---  
 #  Semitones : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The pitch adjustment, in semitones (or half-steps), applied to all sounds in the space. A value of 0 will do nothing, 12 will raise the pitch by an octave and speed up the sound,.
> ``` lang=cpp, name=Zilch
> var Semitones : Real


---  
 #  SoundNodeInput : [soundnode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundnode.markdown)

 `read-only`

> The SoundNode which is the ultimate output of all sounds in this space.
> ``` lang=cpp, name=Zilch
> var SoundNodeInput : SoundNode


---  
 #  SoundNodeOutput : [soundnode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundnode.markdown)

 `read-only`

> The SoundNode which can be used to attach other nodes which should process all audio in the SoundSpace.
> ``` lang=cpp, name=Zilch
> var SoundNodeOutput : SoundNode


---  
 #  Volume : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The volume adjustment applied to all sounds in the space. A value of 1 does nothing, 2 will double the volume, 0.5 will halve it.
> ``` lang=cpp, name=Zilch
> var Volume : Real


---  
 #  Methods


---  
 #  InterpolateDecibels : Void

> Interpolates the SoundSpace's Decibels property from its current value to the value passed in as the first parameter, over the number of seconds passed in as the second parameter.
> |Name|Type|Description|
> |---|---|---|
> |decibels|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |interpolationTime|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function InterpolateDecibels(decibels : Real, interpolationTime : Real)
> ``` 


---  
 #  InterpolatePitch : Void

> Interpolates the SoundSpace's Pitch property from its current value to the value passed in as the first parameter, over the number of seconds passed in as the second parameter.
> |Name|Type|Description|
> |---|---|---|
> |pitch|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |time|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function InterpolatePitch(pitch : Real, time : Real)
> ``` 


---  
 #  InterpolateSemitones : Void

> Interpolates the SoundSpace's Semitones property from its current value to the value passed in as the first parameter, over the number of seconds passed in as the second parameter.
> |Name|Type|Description|
> |---|---|---|
> |pitch|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |time|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function InterpolateSemitones(pitch : Real, time : Real)
> ``` 


---  
 #  InterpolateVolume : Void

> Interpolates the SoundSpace's Volume property from its current value to the value passed in as the first parameter, over the number of seconds passed in as the second parameter.
> |Name|Type|Description|
> |---|---|---|
> |value|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |interpolationTime|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function InterpolateVolume(value : Real, interpolationTime : Real)
> ``` 


---  
 #  PlayCue : [soundinstance](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundinstance.markdown)

> Plays the passed-in SoundCue non-positionally and returns the resulting SoundInstance.
> |Name|Type|Description|
> |---|---|---|
> |cue|[soundcue](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown)| |
> ``` lang=cpp, name=Zilch
> function PlayCue(cue : SoundCue) : SoundInstance
> ``` 


---  
 #  PlayCuePaused : [soundinstance](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundinstance.markdown)

> Plays the passed-in SoundCue non-positionally and returns the resulting SoundInstance, which starts off paused.
> |Name|Type|Description|
> |---|---|---|
> |cue|[soundcue](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown)| |
> ``` lang=cpp, name=Zilch
> function PlayCuePaused(cue : SoundCue) : SoundInstance
> ``` 


---  
 #  SoundSpace : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function SoundSpace()
> ``` 


---  
 
  
  
  
  
  
  
  

 