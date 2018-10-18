 `Component` `Sound`



(NOTE) Plays a specified SoundCue, either when created or when the Play method is called.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Play](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/simplesound.markdown#play-zero-engine-documen)|[ Cue](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/simplesound.markdown#cue-zero-engine-document)|[component](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/component.markdown)| |
|[ Constructor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/simplesound.markdown#simplesound-void)|[ IsPlaying](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/simplesound.markdown#isplaying-zero-engine-do)| | |
|[ Stop](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/simplesound.markdown#stop-void)|[ Paused](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/simplesound.markdown#paused-zero-engine-docum)| | |
| |[ Positional](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/simplesound.markdown#positional-zero-engine-d)| | |
| |[ StartPlaying](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/simplesound.markdown#startplaying-zero-engine)| | |


 #  Properties


---  
 #  Cue : [soundcue](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundcue.markdown)

> 
> ``` lang=cpp, name=Zilch
> var Cue : SoundCue


---  
 #  IsPlaying : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

 `read-only`

> Will be true if the SoundCue is currently being played.
> ``` lang=cpp, name=Zilch
> var IsPlaying : Boolean


---  
 #  Paused : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Setting this Property to true will pause a currently playing SoundCue. Setting it to false will resume playback.
> ``` lang=cpp, name=Zilch
> var Paused : Boolean


---  
 #  Positional : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> If this property is true the SoundCue will be played positionally (heard at a specific location by SoundListeners) through the SoundEmitter component on the same object. If false, the SoundCue will be played through the SoundSpace, and will NOT be affected by any SoundEmitter settings.
> ``` lang=cpp, name=Zilch
> var Positional : Boolean


---  
 #  StartPlaying : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> If this property is true the SoundCue will begin playing as soon as the object is created.
> ``` lang=cpp, name=Zilch
> var StartPlaying : Boolean


---  
 #  Methods


---  
 #  Play : [soundinstance](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundinstance.markdown)

> Begins playing the SoundCue chosen in the Cue property and returns the resulting SoundInstance. If already playing it will be stopped and re-started.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Play() : SoundInstance
> ``` 


---  
 #  SimpleSound : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function SimpleSound()
> ``` 


---  
 #  Stop : Void

> Stops a currently playing SoundInstance if it exists.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Stop()
> ``` 


---  
 
  
  
  
  
  
  
  

 