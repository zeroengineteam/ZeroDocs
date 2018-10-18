 `Sound`

(NOTE) Changes the left and right channel volumes of its input SoundNode's audio separately.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ InterpolateLeftVolume](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/panningnode.markdown#interpolateleftvolume-vo)|[ LeftVolume](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/panningnode.markdown#leftvolume-zero-engine-d)|[soundnode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundnode.markdown)| |
|[ InterpolateRightVolume](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/panningnode.markdown#interpolaterightvolume-v)|[ RightVolume](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/panningnode.markdown#rightvolume-zero-engine)| | |
|[ InterpolateVolumes](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/panningnode.markdown#interpolatevolumes-void)|[ SumToMono](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/panningnode.markdown#sumtomono-zero-engine-do)| | |


 #  Properties


---  
 #  LeftVolume : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The volume multiplier applied to audio in the left channel.
> ``` lang=cpp, name=Zilch
> var LeftVolume : Real


---  
 #  RightVolume : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The volume multiplier applied to audio in the right channel.
> ``` lang=cpp, name=Zilch
> var RightVolume : Real


---  
 #  SumToMono : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

> If this property is true, the audio will be combined into a single channel before being split between the right and left channels. If it is false and the audio has more than two channels, it will be combined into only two channels before being processed.
> ``` lang=cpp, name=Zilch
> var SumToMono : Boolean


---  
 #  Methods


---  
 #  InterpolateLeftVolume : Void

> Interpolates the LeftVolume property from its current value to the value passed in as the first parameter, over the number of seconds passed in as the second parameter.
> |Name|Type|Description|
> |---|---|---|
> |volume|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |time|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function InterpolateLeftVolume(volume : Real, time : Real)
> ``` 


---  
 #  InterpolateRightVolume : Void

> Interpolates the RightVolume property from its current value to the value passed in as the first parameter, over the number of seconds passed in as the second parameter.
> |Name|Type|Description|
> |---|---|---|
> |volume|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |time|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function InterpolateRightVolume(volume : Real, time : Real)
> ``` 


---  
 #  InterpolateVolumes : Void

> Interpolates both left and right volume properties at once. The first parameter is the value to change the LeftVolume to, the second is the RightVolume, and the third is the number of seconds to use for the interpolation.
> |Name|Type|Description|
> |---|---|---|
> |leftVolume|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |rightVolume|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |time|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function InterpolateVolumes(leftVolume : Real, rightVolume : Real, time : Real)
> ``` 


---  
 

 