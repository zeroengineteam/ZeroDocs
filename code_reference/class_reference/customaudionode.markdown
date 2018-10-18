 `Sound`

(NOTE) Uses a SoundBuffer to send audio data directly to the audio engine.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ SendBuffer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/customaudionode.markdown#sendbuffer-void)|[ Channels](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/customaudionode.markdown#channels-zero-engine-doc)|[soundnode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundnode.markdown)| |
|[ SendMicCompressedData](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/customaudionode.markdown#sendmiccompresseddata-vo)|[ MinimumBufferSize](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/customaudionode.markdown#minimumbuffersize-zero-e)| | |
|[ SendMicUncompressedData](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/customaudionode.markdown#sendmicuncompresseddata)|[ SystemSampleRate](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/customaudionode.markdown#systemsamplerate-zero-en)| | |
|[ SendPartialBuffer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/customaudionode.markdown#sendpartialbuffer-void)| | | |


 #  Properties


---  
 #  Channels : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

> The number of audio channels that will be in the buffer.
> ``` lang=cpp, name=Zilch
> var Channels : Integer


---  
 #  MinimumBufferSize : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> The minimum number of samples that should be sent when a NeedMoreSamples event is received.
> ``` lang=cpp, name=Zilch
> var MinimumBufferSize : Integer


---  
 #  SystemSampleRate : [integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)

 `read-only`

> The sample rate currently being used by the audio system.
> ``` lang=cpp, name=Zilch
> var SystemSampleRate : Integer


---  
 #  Methods


---  
 #  SendBuffer : Void

> Sends a buffer of audio samples to the audio system for output.
> |Name|Type|Description|
> |---|---|---|
> |buffer|[soundbuffer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundbuffer.markdown)| |
> ``` lang=cpp, name=Zilch
> function SendBuffer(buffer : SoundBuffer)
> ``` 


---  
 #  SendMicCompressedData : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ||Array[[byte](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/byte.markdown)]| |
> ``` lang=cpp, name=Zilch
> function SendMicCompressedData( : Array[Byte])
> ``` 


---  
 #  SendMicUncompressedData : Void

> 
> |Name|Type|Description|
> |---|---|---|
> ||Array[[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)]| |
> ``` lang=cpp, name=Zilch
> function SendMicUncompressedData( : Array[Real])
> ``` 


---  
 #  SendPartialBuffer : Void

> Sends a partial buffer of audio samples to the audio system for output.
> |Name|Type|Description|
> |---|---|---|
> |buffer|[soundbuffer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundbuffer.markdown)| |
> |startAtIndex|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> |howManySamples|[integer](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/integer.markdown)| |
> ``` lang=cpp, name=Zilch
> function SendPartialBuffer(buffer : SoundBuffer, startAtIndex : Integer, howManySamples : Integer)
> ``` 


---  
 

 