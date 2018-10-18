The [ CustomAudioNode ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customaudionode.markdown) allows the user to provide buffers of custom audio data to the system for output, using a [ SoundBuffer ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundbuffer.markdown) object. 

 # Common Uses

- Playing user-generated pre-computed audio

 # Using the CustomAudioNode

NOTE: This is a fairly limited and high-latency way to output audio. The audio data must be in floating-point numbers between `-1.0` and `1.0`, and it must match the sample rate of the audio engine, which is provided via the `SystemSampleRate` property.

To output audio using a CustomAudioNode the user must connect to the CustomAudioNode's `NeedMoreSamples` event and send a buffer of audio samples when the event is received which is at least as large as the `MinimumBufferSize`. The CustomAudioNode will work best when the audio data is pre-computed and as little as possible is done when the event is received. If the data is not received quickly enough by the audio engine there may be clicks or gaps in the audio. 

The following code block illustrates how to use a CustomAudioNode and a SoundBuffer to generate a single audio channel with a constant Sine tone.
```lang=csharp
// Create and store the CustomAudioNode object
var CustomNode : CustomAudioNode = Audio.CustomAudioNode();

// Create and store the SoundBuffer object
var Buffer : SoundBuffer = Audio.SoundBuffer();

function Initialize(init : CogInitializer)
{
  // Connect to the NeedMoreSamples event of the CustomAudioNode
  Zero.Connect(this.CustomNode, Events.NeedMoreSamples, this.OnSoundEvent);
  
  // Get the minimum buffer size from the CustomAudioNode
  var bufferSize = this.CustomNode.MinimumBufferSize;
  
  var twoPi = 2.0 * Math.Pi;
  var volume = 0.25;
  var buffersPerSecond = this.CustomNode.SystemSampleRate / bufferSize;
  
  // Fill the SoundBuffer with Sine wave values at a frequency that fits evenly into the buffer
  for (var i = 0; i < bufferSize; ++i)
  {
      this.Buffer.AddSampleToBuffer(Math.Sin(twoPi * buffersPerSecond * i / bufferSize) * volume);
  }
  
  // Add the CustomAudioNode to the SoundSpace's SoundNode
  this.Space.SoundSpace.InputNode.AddInputNode(this.CustomNode);
}

function OnSoundEvent(event : SoundEvent)
{
  // Send the buffer of Sine wave samples
  this.CustomNode.SendBuffer(this.Buffer);
}
```

---
 # Related Materials
 ## Manual
- [soudnode_overview](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/audio/soundnode/soudnode_overview.markdown)

 ## Code Reference
- [ CustomAudioNode ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/customaudionode.markdown)
- [ SoundBuffer ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/soundbuffer.markdown) 
  
  
  
  
  
  
  

 