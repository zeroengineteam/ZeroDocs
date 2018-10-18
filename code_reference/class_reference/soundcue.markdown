 `Resource` `Sound`



(NOTE) Settings and Sounds for playing audio files.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ AddSoundEntry](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#addsoundentry-void)|[ Attenuator](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#attenuator-zero-engine-d)|[dataresource](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/dataresource.markdown)| |
|[ AddSoundTagEntry](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#addsoundtagentry-void)|[ BeatsPerMinute](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#beatsperminute-zero-engi)| | |
|[ PlayCueOnNode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#playcueonnode-zero-engin)|[ Decibels](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#decibels-zero-engine-doc)| | |
|[ Preview](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#preview-void)|[ DecibelVariation](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#decibelvariation-zero-en)| | |
|[ StopPreview](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#stoppreview-void)|[ Pitch](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#pitch-zero-engine-docume)| | |
| |[ PitchVariation](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#pitchvariation-zero-engi)| | |
| |[ PlayMode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#playmode-zero-engine-doc)| | |
| |[ SelectMode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#selectmode-zero-engine-d)| | |
| |[ Semitones](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#semitones-zero-engine-do)| | |
| |[ SemitoneVariation](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#semitonevariation-zero-e)| | |
| |[ ShowMusicOptions](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#showmusicoptions-zero-en)| | |
| |[ Sounds](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#sounds-zero-engine-docum)| | |
| |[ SoundTags](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#soundtags-zero-engine-do)| | |
| |[ TimeSigBeats](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#timesigbeats-zero-engine)| | |
| |[ TimeSigValue](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#timesigvalue-zero-engine)| | |
| |[ UseDecibelVariation](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#usedecibelvariation-zero)| | |
| |[ UseSemitoneVariation](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#usesemitonevariation-zer)| | |
| |[ Volume](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#volume-zero-engine-docum)| | |
| |[ VolumeVariation](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown#volumevariation-zero-eng)| | |


 #  Properties


---  
 #  Attenuator : [soundattenuator](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundattenuator.markdown)

> If a SoundAttenuator resource is selected, it will be applied to reduce the sound's volume with distance when played through a SoundEmitter. If DefaultNoAttenuation is selected on the SoundCue and a different SoundAttenuator is selected on the SoundEmitter, the SoundEmitter's settings will be applied. If DefaultNoAttenuation is selected on both the sound will not be attenuated.
> ``` lang=cpp, name=Zilch
> var Attenuator : SoundAttenuator


---  
 #  BeatsPerMinute : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The speed of the music, using beats per minute.
> ``` lang=cpp, name=Zilch
> var BeatsPerMinute : Real


---  
 #  Decibels : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The volume adjustment, in decibels, that will be applied to the sound when it plays. A value of 0 does nothing, 6 will double the sound's volume, -6 will halve it. The Decibels property is linked to the Volume property (changing one will change the other).
> ``` lang=cpp, name=Zilch
> var Decibels : Real


---  
 #  DecibelVariation : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> Sets how much the Decibels will be randomized every time the SoundCue plays. If Decibels is 0, and DecibelVariation is 4, the volume adjustment will be chosen randomly between -4 and 4.
> ``` lang=cpp, name=Zilch
> var DecibelVariation : Real


---  
 #  Pitch : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> This property affects both the pitch and speed of the sound played by the SoundCue. A value of 0 will do nothing, 1 will raise the pitch by an octave and speed up the sound,.
> ``` lang=cpp, name=Zilch
> var Pitch : Real


---  
 #  PitchVariation : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> Sets how much the pitch will be randomized every time the SoundCue plays. If Pitch is 0, and PitchVariation is 0.3, the pitch of the sound will be chosen randomly between -0.3 and 0.3.
> ``` lang=cpp, name=Zilch
> var PitchVariation : Real


---  
 #  PlayMode : [SoundPlayMode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#soundplaymode)

> If Single is chosen the SoundInstance created by the SoundCue will be played once and will stop when it reaches its EndTime. If Looping is chosen the SoundInstance will play continuously until either it is stopped or its Looping property is set to false.
> ``` lang=cpp, name=Zilch
> var PlayMode : SoundPlayMode


---  
 #  SelectMode : [SoundSelectMode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/enum_reference.markdown#soundselectmode)

> If Random is chosen the SoundCue will randomly choose which SoundEntry to play. If Sequential is chosen it will play the SoundEntries in order.
> ``` lang=cpp, name=Zilch
> var SelectMode : SoundSelectMode


---  
 #  Semitones : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> This property, specified in semitones (or half-steps), affects both the pitch and speed of the sound played by the SoundCue. A value of 0 will do nothing, 12 will raise the pitch by an octave and speed up the sound, and -12 will lower the sound by an octave and slow it down. The Semitones property is linked to the Pitch property (changing one will change the other).
> ``` lang=cpp, name=Zilch
> var Semitones : Real


---  
 #  SemitoneVariation : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> Sets how much the pitch will be randomized every time the SoundCue plays. If Semitones is 0, and SemitoneVariation is 5, the pitch of the sound will be chosen randomly between -5 and 5.
> ``` lang=cpp, name=Zilch
> var SemitoneVariation : Real


---  
 #  ShowMusicOptions : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> If true, the music options will be shown. If false, they will be hidden.
> ``` lang=cpp, name=Zilch
> var ShowMusicOptions : Boolean


---  
 #  Sounds : [sounds](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sounds.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Sounds : Sounds


---  
 #  SoundTags : [soundtags](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtags.markdown)

> 
> ``` lang=cpp, name=Zilch
> var SoundTags : SoundTags


---  
 #  TimeSigBeats : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The top number of the music's time signature (beats per measure).
> ``` lang=cpp, name=Zilch
> var TimeSigBeats : Real


---  
 #  TimeSigValue : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The bottom number of the music's time signature (which type of note has the beat).
> ``` lang=cpp, name=Zilch
> var TimeSigValue : Real


---  
 #  UseDecibelVariation : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> If false, the VolumeVariation value will be used to randomize the volume. If true, the DecibelVariation field will be shown and will be used for randomization.
> ``` lang=cpp, name=Zilch
> var UseDecibelVariation : Boolean


---  
 #  UseSemitoneVariation : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> If false, the PitchVariation value will be used to randomize the volume. If true, the SemitoneVariation field will be shown and will be used for randomization.
> ``` lang=cpp, name=Zilch
> var UseSemitoneVariation : Boolean


---  
 #  Volume : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The volume adjustment that will be applied to the sound when it plays. A value of 1 does nothing, 2 will double the sound's volume, 0.5 will halve it. The Volume property is linked to the Decibels property (changing one will change the other).
> ``` lang=cpp, name=Zilch
> var Volume : Real


---  
 #  VolumeVariation : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> Sets how much the Volume will be randomized every time the SoundCue plays. If Volume is 1, and VolumeVariation is 0.5, the volume adjustment will be chosen randomly between 0.5 and 1.5.
> ``` lang=cpp, name=Zilch
> var VolumeVariation : Real


---  
 #  Methods


---  
 #  AddSoundEntry : Void

> Adds a new SoundEntry to this SoundCue.
> |Name|Type|Description|
> |---|---|---|
> |sound|[sound](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/sound.markdown)| |
> |weight|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddSoundEntry(sound : Sound, weight : Real)
> ``` 


---  
 #  AddSoundTagEntry : Void

> Adds a new SoundTagEntry to this SoundCue.
> |Name|Type|Description|
> |---|---|---|
> |soundTag|[soundtag](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddSoundTagEntry(soundTag : SoundTag)
> ``` 


---  
 #  PlayCueOnNode : [soundinstance](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundinstance.markdown)

> Plays this SoundCue using a specified SoundNode as the output and returns the resulting SoundInstance.
> |Name|Type|Description|
> |---|---|---|
> |outputNode|[soundnode](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundnode.markdown)| |
> |startPaused|[boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)| |
> ``` lang=cpp, name=Zilch
> function PlayCueOnNode(outputNode : SoundNode, startPaused : Boolean) : SoundInstance
> ``` 


---  
 #  Preview : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Preview()
> ``` 


---  
 #  StopPreview : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function StopPreview()
> ``` 


---  
 
  
  
  
  
  
  
  

 