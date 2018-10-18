 `Component` `Sound`



|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/audiosettings.markdown#audiosettings-void)|[ LatencySetting](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/audiosettings.markdown#latencysetting-zero-engi)|[component](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/component.markdown)| |
| |[ MinVolumeThreshold](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/audiosettings.markdown#minvolumethreshold-zero)| | |
| |[ MixType](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/audiosettings.markdown#mixtype-zero-engine-docu)| | |
| |[ MuteAllAudio](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/audiosettings.markdown#muteallaudio-zero-engine)| | |
| |[ SystemVolume](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/audiosettings.markdown#systemvolume-zero-engine)| | |


 #  Properties


---  
 #  LatencySetting : [AudioLatency](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#audiolatency)

> Using the high latency setting can fix some audio problems (such as clicks and static) but can lead to a slight delay in the audio.
> ``` lang=cpp, name=Zilch
> var LatencySetting : AudioLatency


---  
 #  MinVolumeThreshold : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> Sets the volume threshold at which sounds will be virtualized (they will continue tracking their position and all data but will not process audio). This is a floating point volume number, not decibels.
> ``` lang=cpp, name=Zilch
> var MinVolumeThreshold : Real


---  
 #  MixType : [AudioMixTypes](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#audiomixtypes)

> Sets the number of channels the audio system uses when creating audio. See the enum descriptions. If your selection is different from the output device, it will be automatically translated to match the number of channels needed for output.
> ``` lang=cpp, name=Zilch
> var MixType : AudioMixTypes


---  
 #  MuteAllAudio : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> When true, audio will be processed normally but will be silent.
> ``` lang=cpp, name=Zilch
> var MuteAllAudio : Boolean


---  
 #  SystemVolume : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> An overall volume modifier that is applied to all audio produced by Zero.
> ``` lang=cpp, name=Zilch
> var SystemVolume : Real


---  
 #  Methods


---  
 #  AudioSettings : Void

 `constructor`

> 
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function AudioSettings()
> ``` 


---  
 

 