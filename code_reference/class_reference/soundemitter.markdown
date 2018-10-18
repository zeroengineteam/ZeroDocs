 `Component` `Sound`



(NOTE) Allows 3D positioning of sounds relative to SoundListeners.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ InterpolateDecibels](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#interpolatedecibels-void)|[ Attenuator](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#attenuator-zero-engine-d)|[component](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/component.markdown)| |
|[ InterpolatePitch](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#interpolatepitch-void)|[ Decibels](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#decibels-zero-engine-doc)| | |
|[ InterpolateSemitones](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#interpolatesemitones-voi)|[ Directional](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#directional-zero-engine)| | |
|[ InterpolateVolume](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#interpolatevolume-void)|[ EmitAngle](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#emitangle-zero-engine-do)| | |
|[ PlayCue](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#playcue-zero-engine-docu)|[ InputNode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#inputnode-zero-engine-do)| | |
|[ PlayCuePaused](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#playcuepaused-zero-engin)|[ IsPlaying](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#isplaying-zero-engine-do)| | |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#soundemitter-void)|[ OutputNode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#outputnode-zero-engine-d)| | |
| |[ Paused](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#paused-zero-engine-docum)| | |
| |[ Pitch](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#pitch-zero-engine-docume)| | |
| |[ RearVolume](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#rearvolume-zero-engine-d)| | |
| |[ Semitones](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#semitones-zero-engine-do)| | |
| |[ SoundNodeInput](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#soundnodeinput-zero-engi)| | |
| |[ SoundNodeOutput](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#soundnodeoutput-zero-eng)| | |
| |[ Volume](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundemitter.markdown#volume-zero-engine-docum)| | |


 #  Properties


---  
 #  Attenuator : [soundattenuator](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundattenuator.markdown)

> If a SoundAttenuator resource other than DefaultNoAttenuation is selected it will be applied to SoundCues without their own SoundAttenuator resource. If a SoundCue has attenuation settings those will always be used. If neither has settings, the sound will not be attenuated.
> ``` lang=cpp, name=Zilch
> var Attenuator : SoundAttenuator


---  
 #  Decibels : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The volume adjustment, in decibels, applied to all sounds played through this SoundEmitter. A value of 0 does nothing, 6 will double the volume, -6 will halve it. The Decibels property is linked to the Volume property (changing one will change the other).
> ``` lang=cpp, name=Zilch
> var Decibels : Real


---  
 #  Directional : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> When true, the audio output of the SoundEmitter will be limited by the EmitAngle, so that sound in front of the object will be louder than sound behind it. Within the EmitAngle the sound will be at full volume. The volume interpolates logarithmically until it reaches the RearVolume value directly behind the object.
> ``` lang=cpp, name=Zilch
> var Directional : Boolean


---  
 #  EmitAngle : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The angle of full volume sound for a directional SoundEmitter, from 1 to 360. An angle of 90, for example, will be centered at the object's front, extending 45 degrees to the left and right.
> ``` lang=cpp, name=Zilch
> var EmitAngle : Real


---  
 #  InputNode : [soundnode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundnode.markdown)

 `read-only`

> DEPRECATED The SoundNodeInput property should be used instead.
> ``` lang=cpp, name=Zilch
> var InputNode : SoundNode


---  
 #  IsPlaying : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> This property will be true if there are SoundInstances currently associated with this SoundEmitter, even if they are paused or otherwise not audible.
> ``` lang=cpp, name=Zilch
> var IsPlaying : Boolean


---  
 #  OutputNode : [soundnode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundnode.markdown)

 `read-only`

> DEPRECATED The SoundNodeOutput property should be used instead.
> ``` lang=cpp, name=Zilch
> var OutputNode : SoundNode


---  
 #  Paused : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Setting this property to true pauses all sounds currently playing through the SoundEmitter. Setting it to false will resume playback.
> ``` lang=cpp, name=Zilch
> var Paused : Boolean


---  
 #  Pitch : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> This property affects both the pitch and speed of all sounds played through this SoundEmitter. A value of 0 will do nothing, 1 will raise the pitch by an octave and speed up the sound, -1 will lower the sound by an octave and slow it down. The Pitch property is linked to the Semitones property (changing one will change the other).
> ``` lang=cpp, name=Zilch
> var Pitch : Real


---  
 #  RearVolume : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The volume of sound heard directly behind a directional SoundEmitter. It will only reach this value in a small area, since volume is interpolated from the edge of the EmitAngle. To make the volume as quiet as possible behind the object, use a small EmitAngle.
> ``` lang=cpp, name=Zilch
> var RearVolume : Real


---  
 #  Semitones : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> This property, specified in semitones (or half-steps), affects both the pitch and speed of all sounds played through this SoundEmitter.. A value of 0 will do nothing, 12 will raise the pitch by an octave and speed up the sound, -12 will lower the sound by an octave and slow it down. The Semitones property is linked to the Pitch property (changing one will change the other).
> ``` lang=cpp, name=Zilch
> var Semitones : Real


---  
 #  SoundNodeInput : [soundnode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundnode.markdown)

 `read-only`

> The SoundNode to use for attaching other nodes to the input of the SoundEmitter.
> ``` lang=cpp, name=Zilch
> var SoundNodeInput : SoundNode


---  
 #  SoundNodeOutput : [soundnode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundnode.markdown)

 `read-only`

> The SoundNode to use for attaching other nodes to the output of the SoundEmitter.
> ``` lang=cpp, name=Zilch
> var SoundNodeOutput : SoundNode


---  
 #  Volume : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The volume adjustment applied to all sounds played through this SoundEmitter. A value of 1 does nothing, 2 will double the volume, 0.5 will halve it. The Volume property is linked to the Decibels property (changing one will change the other).
> ``` lang=cpp, name=Zilch
> var Volume : Real


---  
 #  Methods


---  
 #  InterpolateDecibels : Void

> Interpolates the Decibels property from its current value to the value passed in as the first parameter, over the number of seconds passed in as the second parameter.
> |Name|Type|Description|
> |---|---|---|
> |decibels|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |interpolationTime|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function InterpolateDecibels(decibels : Real, interpolationTime : Real)
> ``` 


---  
 #  InterpolatePitch : Void

> Interpolates the Pitch property from its current value to the value passed in as the first parameter, over the number of seconds passed in as the second parameter.
> |Name|Type|Description|
> |---|---|---|
> |pitch|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |interpolationTime|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function InterpolatePitch(pitch : Real, interpolationTime : Real)
> ``` 


---  
 #  InterpolateSemitones : Void

> Interpolates the Semitones property from its current value to the value passed in as the first parameter, over the number of seconds passed in as the second parameter.
> |Name|Type|Description|
> |---|---|---|
> |pitch|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |interpolationTime|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function InterpolateSemitones(pitch : Real, interpolationTime : Real)
> ``` 


---  
 #  InterpolateVolume : Void

> Interpolates the Volume property from its current value to the value passed in as the first parameter, over the number of seconds passed in as the second parameter.
> |Name|Type|Description|
> |---|---|---|
> |volume|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |interpolationTime|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function InterpolateVolume(volume : Real, interpolationTime : Real)
> ``` 


---  
 #  PlayCue : [soundinstance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundinstance.markdown)

> Plays the SoundCue passed into the function and returns the resulting SoundInstance.
> |Name|Type|Description|
> |---|---|---|
> |cue|[soundcue](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundcue.markdown)| |
> ``` lang=cpp, name=Zilch
> function PlayCue(cue : SoundCue) : SoundInstance
> ``` 


---  
 #  PlayCuePaused : [soundinstance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundinstance.markdown)

> Plays the SoundCue passed into the function and returns the resulting SoundInstance, which starts off paused.
> |Name|Type|Description|
> |---|---|---|
> |cue|[soundcue](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundcue.markdown)| |
> ``` lang=cpp, name=Zilch
> function PlayCuePaused(cue : SoundCue) : SoundInstance
> ``` 


---  
 #  SoundEmitter : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function SoundEmitter()
> ``` 


---  
 

 