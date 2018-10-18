 `Resource` `Sound`



(NOTE) Controls settings on all tagged SoundInstances.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ EQSetAllBands](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#eqsetallbands-void)|[ CompressorAttack](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#compressorattack-zero-en)|[dataresource](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/dataresource.markdown)| |
|[ InterpolateDecibels](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#interpolatedecibels-void)|[ CompressorKneeWidth](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#compressorkneewidth-zero)| | |
|[ InterpolateVolume](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#interpolatevolume-void)|[ CompressorRatio](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#compressorratio-zero-eng)| | |
|[ StopSounds](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#stopsounds-void)|[ CompressorRelease](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#compressorrelease-zero-e)| | |
|[ TagSound](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#tagsound-void)|[ CompressorThreshold](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#compressorthreshold-zero)| | |
|[ UnTagSound](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#untagsound-void)|[ Decibels](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#decibels-zero-engine-doc)| | |
| |[ EQBand1Gain](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#eqband1gain-zero-engine)| | |
| |[ EQBand2Gain](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#eqband2gain-zero-engine)| | |
| |[ EQBand3Gain](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#eqband3gain-zero-engine)| | |
| |[ EQHighPassGain](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#eqhighpassgain-zero-engi)| | |
| |[ EQLowPassGain](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#eqlowpassgain-zero-engin)| | |
| |[ InstanceCount](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#instancecount-zero-engin)| | |
| |[ InstanceLimit](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#instancelimit-zero-engin)| | |
| |[ Instances](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#instances-zero-engine-do)| | |
| |[ Paused](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#paused-zero-engine-docum)| | |
| |[ TagForDucking](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#tagforducking-zero-engin)| | |
| |[ UseCompressor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#usecompressor-zero-engin)| | |
| |[ UseEqualizer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#useequalizer-zero-engine)| | |
| |[ Volume](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown#volume-zero-engine-docum)| | |


 #  Properties


---  
 #  CompressorAttack : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The time, in milliseconds, for the filter to ramp to full effect after the input reaches the threshold.
> ``` lang=cpp, name=Zilch
> var CompressorAttack : Real


---  
 #  CompressorKneeWidth : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The knee width of the filter, in decibels.
> ``` lang=cpp, name=Zilch
> var CompressorKneeWidth : Real


---  
 #  CompressorRatio : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The ratio of the compression applied by the filter.
> ``` lang=cpp, name=Zilch
> var CompressorRatio : Real


---  
 #  CompressorRelease : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The time, in milliseconds, for the filter to ramp from full effect to off after the input drops below the threshold.
> ``` lang=cpp, name=Zilch
> var CompressorRelease : Real


---  
 #  CompressorThreshold : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The threshold, in decibels, at which the volume is affected by the filter.
> ``` lang=cpp, name=Zilch
> var CompressorThreshold : Real


---  
 #  Decibels : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The volume adjustment, in decibels, applied to all tagged instances.
> ``` lang=cpp, name=Zilch
> var Decibels : Real


---  
 #  EQBand1Gain : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The volume adjustment applied to frequencies within the band centered at 150 Hz. Positive values will boost these frequencies while negative values will reduce them.
> ``` lang=cpp, name=Zilch
> var EQBand1Gain : Real


---  
 #  EQBand2Gain : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The volume adjustment applied to frequencies within the band centered at 600 Hz. Positive values will boost these frequencies while negative values will reduce them.
> ``` lang=cpp, name=Zilch
> var EQBand2Gain : Real


---  
 #  EQBand3Gain : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The volume adjustment applied to frequencies within the band centered at 2500 Hz. Positive values will boost these frequencies while negative values will reduce them.
> ``` lang=cpp, name=Zilch
> var EQBand3Gain : Real


---  
 #  EQHighPassGain : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The volume adjustment applied to frequencies above 5000 Hz. Positive values will boost these frequencies while negative values will reduce them.
> ``` lang=cpp, name=Zilch
> var EQHighPassGain : Real


---  
 #  EQLowPassGain : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The volume adjustment applied to frequencies below 80 Hz. Positive values will boost these frequencies while negative values will reduce them.
> ``` lang=cpp, name=Zilch
> var EQLowPassGain : Real


---  
 #  InstanceCount : [integer](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> The number of SoundInstances currently associated with this SoundTag.
> ``` lang=cpp, name=Zilch
> var InstanceCount : Integer


---  
 #  InstanceLimit : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> If this value is greater than zero, SoundCues with this SoundTag will only play if the number of tagged SoundInstances is less than this number.
> ``` lang=cpp, name=Zilch
> var InstanceLimit : Real


---  
 #  Instances : [soundinstancerange](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundinstancerange.markdown)

 `read-only`

> This allows you to get all currently tagged SoundInstances. Using a foreach loop, you can access any SoundInstance functionality on each of the tagged instances.
> ``` lang=cpp, name=Zilch
> var Instances : SoundInstanceRange


---  
 #  Paused : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> Setting this property to true will pause all tagged instances. Setting it to false will resume playback.
> ``` lang=cpp, name=Zilch
> var Paused : Boolean


---  
 #  TagForDucking : [soundtag](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundtag.markdown)

> If this property is not null, the selected SoundTag will be used to trigger this SoundTag's compressor.
> ``` lang=cpp, name=Zilch
> var TagForDucking : SoundTag


---  
 #  UseCompressor : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> If true, the SoundTag's compressor settings will be applied to the tagged SoundInstances.
> ``` lang=cpp, name=Zilch
> var UseCompressor : Boolean


---  
 #  UseEqualizer : [boolean](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/boolean.markdown)

> If true, the SoundTag's equalizer settings will be applied to the tagged SoundInstances.
> ``` lang=cpp, name=Zilch
> var UseEqualizer : Boolean


---  
 #  Volume : [real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)

> The volume adjustment applied to all tagged instances.
> ``` lang=cpp, name=Zilch
> var Volume : Real


---  
 #  Methods


---  
 #  EQSetAllBands : Void

> Sets all equalizer band gain values at once. The parameters are in order from the lowest band to the highest. The last parameter is the number of seconds to interpolate the values over.
> |Name|Type|Description|
> |---|---|---|
> |lowPass|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |band1|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |band2|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |band3|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |highPass|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |timeToInterpolate|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function EQSetAllBands(lowPass : Real, band1 : Real, band2 : Real, band3 : Real, highPass : Real, timeToInterpolate : Real)
> ``` 


---  
 #  InterpolateDecibels : Void

> Interpolates the SoundTag's Decibels property from its current value to the value passed in as the first parameter, over the number of seconds passed in as the second parameter.
> |Name|Type|Description|
> |---|---|---|
> |decibels|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |interpolationTime|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function InterpolateDecibels(decibels : Real, interpolationTime : Real)
> ``` 


---  
 #  InterpolateVolume : Void

> Interpolates the SoundTag's Volume property from its current value to the value passed in as the first parameter, over the number of seconds passed in as the second parameter.
> |Name|Type|Description|
> |---|---|---|
> |value|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |interpolationTime|[real](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function InterpolateVolume(value : Real, interpolationTime : Real)
> ``` 


---  
 #  StopSounds : Void

> Stops all currently tagged SoundInstances.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function StopSounds()
> ``` 


---  
 #  TagSound : Void

> Adds a new SoundInstance to this SoundTag.
> |Name|Type|Description|
> |---|---|---|
> |instance|[soundinstance](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundinstance.markdown)| |
> ``` lang=cpp, name=Zilch
> function TagSound(instance : SoundInstance)
> ``` 


---  
 #  UnTagSound : Void

> Removes a SoundInstance from this SoundTag.
> |Name|Type|Description|
> |---|---|---|
> |instance|[soundinstance](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundinstance.markdown)| |
> ``` lang=cpp, name=Zilch
> function UnTagSound(instance : SoundInstance)
> ``` 


---  
 
  
  
  
  
  
  
  

 