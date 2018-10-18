The [ PanningNode ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/panningnode.markdown) collects audio data from all of its inputs and applies a volume modification to the left and right channels separately. 

 # Common Uses

- Moving sounds from left to right and right to left (such as an ambient wind sound)
- Positioning sounds without using a [SoundEmitter ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundnode/soundemitter.markdown)

 # Using the PanningNode

PanningNodes will always process audio in two channels regardless of how many channels are used by their inputs or outputs. If the audio input has more than two channels it will be translated into only two before being processed.

 ## SumToMono

If the `SumToMono` property is set to `true`, all channels of audio input will be combined before being spread to the left and right channels with the appropriate volume modification. This can be useful if you want the entire sound to be heard as if it is coming from a single position (this is how audio is handled by SoundEmitters). If it is `false`, the volume modifications will be applied to the existing channels. 

 ## Events

The `AudioInterpolationDone` event will be sent when a volume interpolation has finished.

 ## Example

The following code block illustrates how to make white noise sound like it's moving back and forth.

```lang=csharp
class MovingNoise : ZilchComponent
{
  // Create and store the PanningNode to change its properties later
  var Panning : PanningNode = Audio.PanningNode();
  
  // Create and store the GeneratedWaveNode
  var Noise : GeneratedWaveNode = Audio.GeneratedWaveNode();
  
  function Initialize(init : CogInitializer)
  {
    // Set the GeneratedWaveNode properties
    this.Noise.WaveType = SynthWaveType.Noise;
    this.Noise.Volume = 0.2;
    
    // Start playing the generated sound wave
    this.Noise.Play();
    
    // Reduce the PanningNode's left volume
    this.Panning.LeftVolume = 0.3;
    
    // Add the GeneratedWaveNode to the inputs of the PanningNode
    this.Panning.AddInputNode(this.Noise);
    
    // Attach the PanningNode to the output node of the SoundSpace
    this.Space.SoundSpace.SoundNode.AddInputNode(this.Panning);
    
    // Start panning
    this.ChangePanning();
  }
  
  function ChangePanning()
  {
    var time = 3.0;
    
    // Are we now panning from left to right?
    if (this.Panning.LeftVolume < this.Panning.RightVolume)
    {
      // Interpolate the left volume back to 1.0 and the right volume to 0.2
      this.Panning.InterpolateVolumes(1.0, 0.2, time);
    }
    // If not, we are panning from right to left
    else
    {
      // Interpolate the right volume back to 1.0 and the left volume to 0.2
      this.Panning.InterpolateVolumes(0.2, 1.0, time);
    }
    
    // Delay the next call of this function by the time
    var sequence = Actions.Sequence(this.Owner.Actions);
    Actions.Delay(sequence, time);
    Actions.Call(sequence, this.ChangePanning);
  }
}
```

---
 # Related Materials
 ## Manual
- [soudnode_overview](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundnode/soudnode_overview.markdown)

 ## Code Reference
- [ PanningNode ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/panningnode.markdown) 

 