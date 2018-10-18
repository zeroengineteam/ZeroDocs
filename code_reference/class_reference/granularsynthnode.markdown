 `Sound`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Play](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/granularsynthnode.markdown#play-void)|[ BufferScanRate](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/granularsynthnode.markdown#bufferscanrate-zero-engi)|[soundnode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundnode.markdown)| |
|[ SetSound](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/granularsynthnode.markdown#setsound-void)|[ GrainDelay](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/granularsynthnode.markdown#graindelay-zero-engine-d)| | |
|[ Stop](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/granularsynthnode.markdown#stop-void)|[ GrainDelayVariance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/granularsynthnode.markdown#graindelayvariance-zero)| | |
| |[ GrainLength](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/granularsynthnode.markdown#grainlength-zero-engine)| | |
| |[ GrainLengthVariance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/granularsynthnode.markdown#grainlengthvariance-zero)| | |
| |[ GrainPanningValue](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/granularsynthnode.markdown#grainpanningvalue-zero-e)| | |
| |[ GrainPanningVariance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/granularsynthnode.markdown#grainpanningvariance-zer)| | |
| |[ GrainResampleRate](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/granularsynthnode.markdown#grainresamplerate-zero-e)| | |
| |[ GrainResampleRateVariance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/granularsynthnode.markdown#grainresampleratevarianc)| | |
| |[ GrainVolume](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/granularsynthnode.markdown#grainvolume-zero-engine)| | |
| |[ GrainVolumeVariance](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/granularsynthnode.markdown#grainvolumevariance-zero)| | |
| |[ RandomLocationValue](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/granularsynthnode.markdown#randomlocationvalue-zero)| | |
| |[ WindowAttack](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/granularsynthnode.markdown#windowattack-zero-engine)| | |
| |[ WindowRelease](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/granularsynthnode.markdown#windowrelease-zero-engin)| | |
| |[ WindowType](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/granularsynthnode.markdown#windowtype-zero-engine-d)| | |


 #  Properties


---  
 #  BufferScanRate : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The rate at which the synthesizer scans the buffer as it creates grains. A value of 1.0 will move through the audio data at the same rate as it would normally be played, 0.5 will move at half speed, and -1.0 will move at normal speed backward. A value of 0.0 will make the synthesizer repeat the same audio continuously.
> ``` lang=cpp, name=Zilch
> var BufferScanRate : Real


---  
 #  GrainDelay : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

> The number of milliseconds to wait before playing another grain.
> ``` lang=cpp, name=Zilch
> var GrainDelay : Integer


---  
 #  GrainDelayVariance : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

> The variance for randomizing the grain delay, in milliseconds.
> ``` lang=cpp, name=Zilch
> var GrainDelayVariance : Integer


---  
 #  GrainLength : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

> The length of a grain, in milliseconds.
> ``` lang=cpp, name=Zilch
> var GrainLength : Integer


---  
 #  GrainLengthVariance : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

> The variance for randomizing the grain length, in milliseconds.
> ``` lang=cpp, name=Zilch
> var GrainLengthVariance : Integer


---  
 #  GrainPanningValue : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The value used to pan the grains left or right. A value of 0 will be heard equally from the left and right, 1.0 will be heard only on the right, and -1.0 will be only left.
> ``` lang=cpp, name=Zilch
> var GrainPanningValue : Real


---  
 #  GrainPanningVariance : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The variance for randomizing the grain panning value.
> ``` lang=cpp, name=Zilch
> var GrainPanningVariance : Real


---  
 #  GrainResampleRate : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The rate at which grains resample their audio data. A value of 1.0 will play normally, 0.5 will play at half speed, and -1.0 will play at normal speed backward. Cannot be 0.
> ``` lang=cpp, name=Zilch
> var GrainResampleRate : Real


---  
 #  GrainResampleRateVariance : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The variance for randomizing the grain resample rate.
> ``` lang=cpp, name=Zilch
> var GrainResampleRateVariance : Real


---  
 #  GrainVolume : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The volume modifier applied to the grains.
> ``` lang=cpp, name=Zilch
> var GrainVolume : Real


---  
 #  GrainVolumeVariance : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The variance for randomizing the grain volume.
> ``` lang=cpp, name=Zilch
> var GrainVolumeVariance : Real


---  
 #  RandomLocationValue : [real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)

> The value for controlling how many grains have randomized starting positions in the audio. A value of 0 will be completely sequential, while 1.0 will be completely random.
> ``` lang=cpp, name=Zilch
> var RandomLocationValue : Real


---  
 #  WindowAttack : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

> The window attack time, in milliseconds. Does not have an effect on some windows.
> ``` lang=cpp, name=Zilch
> var WindowAttack : Integer


---  
 #  WindowRelease : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

> The window release time, in milliseconds. Does not have an effect on some windows.
> ``` lang=cpp, name=Zilch
> var WindowRelease : Integer


---  
 #  WindowType : [GranularSynthWindows](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#granularsynthwindows)

> The type of window, or volume envelope, used for each grain.
> ``` lang=cpp, name=Zilch
> var WindowType : GranularSynthWindows


---  
 #  Methods


---  
 #  Play : Void

> Starts playing new grains.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Play()
> ``` 


---  
 #  SetSound : Void

> Sets the Sound resource that will be used for the grains, along with an optional start and stop time. If the stopTime is 0.0, all audio from the Sound will be used.
> |Name|Type|Description|
> |---|---|---|
> |sound|[sound](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/sound.markdown)| |
> |startTime|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |stopTime|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function SetSound(sound : Sound, startTime : Real, stopTime : Real)
> ``` 


---  
 #  Stop : Void

> Stops playing new grains but continues to play current ones.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Stop()
> ``` 


---  
 

 