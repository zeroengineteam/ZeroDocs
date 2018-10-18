The [ GeneratedWaveNode](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/generatedwavenode.markdown) will generate audio using a specified wave type and frequency. Since it is a generating node, it will ignore any input connections.

 # Common Uses

- Creating synthesized sound effects
- Combining white noise with audio filters to generate wind or other sound effects

 # Using the GeneratedWaveNode

GeneratedWaveNodes create audio using either a sine wave, square wave, saw wave, triangle wave, or white noise. The `WaveFrequency` property controls the pitch of the audio, and can be smoothly changed over time using the `InterpolateWaveFrequency` method. Like other objects, its volume can be controlled using either the `Volume` or the `Decibels` property, and interpolated with the `InterpolateVolume` and `InterpolateDecibels` methods.

The following code block illustrates how to use a GeneratedWaveNode to make a simple alarm-siren noise.


```lang=csharp
class SimpleSiren : ZilchComponent
{
  // Make sure this object has a SoundEmitter component
  [Dependency] var Emitter : SoundEmitter;
  
  // Store the GeneratedWaveNode so its properties can be edited later
  var WaveNode : GeneratedWaveNode = Audio.GeneratedWaveNode();

  // Keep track of whether we are interpolating up or down
  var GoingUp : Boolean = true;
  
  function Initialize(init : CogInitializer)
  {
    // Attach the GeneratedWaveNode to the SoundEmitter
    this.Emitter.InputNode.AddInputNode(this.WaveNode);

    // Set the node's starting properties
    this.WaveNode.WaveFrequency = 200.0;
    this.WaveNode.WaveType = SynthWaveType.SawWave;
    this.WaveNode.Volume = 0.2;

    // Start playing the generated wave
    this.WaveNode.Play();

    // Start interpolating the frequency
    this.ChangeFrequency();
  }

  function ChangeFrequency()
  {
    // Check if we should interpolate the frequency up or down
    if (this.GoingUp == true)
    {
      // Interpolate the wave's frequency to 700Hz over 1 second
      this.WaveNode.InterpolateWaveFrequency(700.0, 1.0);

      // Reset the variable to go down next time
      this.GoingUp = false;
    }
    else
    {
      // Interpolate the wave's frequency to 500Hz over 1 second
      this.WaveNode.InterpolateWaveFrequency(500.0, 1.0);

      // Reset the variable to go up next time
      this.GoingUp = true;
    }
    
    // Call this function again in 1.1 seconds
    var sequence = Actions.Sequence(this.Owner.Actions);
    Actions.Delay(sequence, 1.1);
    Actions.Call(sequence, this.ChangeFrequency);
  }
}
```

---
 # Related Materials
 ## Manual
- [soudnode_overview](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundnode/soudnode_overview.markdown)

 ## Code Reference
- [ GeneratedWaveNode ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/generatedwavenode.markdown) 

 