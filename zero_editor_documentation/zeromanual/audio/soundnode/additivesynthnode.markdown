[ AdditiveSynthNodes ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/additivesynthnode.markdown) are basic synthesizers, generating notes using a combination of sound waves.

 ## Common Uses

- A custom synthesizer using [MIDI ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundnode//midi.markdown) events sent by a keyboard or other device
- Creating music or sound effects with no audio files
- Dynamic or procedural music 

 ## Using the AdditiveSynthNode

The AdditiveSynthNode generates audio at specified pitches using additive synthesis, where multiple sound waves at different frequencies are added together to make one sound. Each of these separate waves is called a harmonic. All harmonics have their own volume envelope which controls how quickly the sine wave goes from silence to full volume and back to silence: varying the envelopes for different harmonics will affect how the generated sound changes over time. 

Online tools such as this [waveform generator ](http://meettechniek.info/additional/additive-synthesis.html ) are useful for experimenting with different sounds, though the envelope values and types of sound waves will have a large effect. (This particular tool uses harmonics which are integer multiples of the base frequency, resulting in sounds that always have a distinct pitch.) The code block below showing how to use the `AddHarmonic` method contains a simple example that can be used as a starting point.

 ## Adding Harmonics

The `AddHarmonic` method adds a new harmonic which will be used for all notes played. The first parameter is the base frequency multiplier to use for this sine wave's frequency (i.e. if you play a note at `200` Hz and the multiplier is `2` this sine wave will be at `400` Hz); the second is the volume adjustment applied to this harmonic (`1.0` is full volume); the third is an AdsrEnvelope object containing the envelope-related values (see the AdsrEnvelope section below); and the fourth is the type of sound wave to use. The valid `SynthWaveTypes` to use are `SineWave`, `SquareWave`, `SawWave`, and `TriangleWave`. If you do not fill out the AdsrEnvelope parameters before calling `AddHarmonic` default values will be used.

The following code block shows you how to create a simple instrument with two harmonics.

```lang=csharp
var Synth : AdditiveSynthNode = Audio.AdditiveSynthNode();

function Initialize(init : CogInitializer)
{
    // Adds the AdditiveSynthNode to the SoundSpace's SoundNode for output
    this.Space.SoundSpace.InputNode.AddInputNode(this.Synth);
    
    // Create a variable for the AdsrEnvelope
    var envelope = AdsrEnvelope();
    
    // Set the envelope values for the first harmonic
    envelope.AttackTime = 0.09;
    envelope.DecayTime = 0.5;
    envelope.SustainTime = 0.07;
    envelope.SustainLevel = 0.5;
    envelope.ReleaseTime = 1.0;
    
    // Add the first harmonic to the synth at the base frequency and half volume, using a sine wave
    this.Synth.AddHarmonic(1.0, 0.5, envelope, SynthWaveType.SineWave);
    
    // Set the envelope values for the second harmonic 
    envelope.AttackTime = 0.02;
    envelope.DecayTime = 0;
    envelope.SustainTime = 0.02;
    envelope.SustainLevel = 1.0;
    envelope.ReleaseTime = 0.5;
    
    // Add the second harmonic at triple the base frequency and quarter volume, using a sine wave
    this.Synth.AddHarmonic(3.0, 0.25, envelope, SynthWaveType.SineWave);
}
```

 ## Playing Notes

The `NoteOn` method plays a note at a specific frequency, using MIDI key numbers. The Zero Engine uses the MIDI convention where middle C is considered to be C3 and has the number `60`. (MIDI key number charts such as [this one ](http://computermusicresource.com/midikeys.html ) can be used to translate between notes at different octaves and their corresponding key numbers.) 

The `NoteOff` method stops any currently playing notes with the specified MIDI key number. The notes will jump to their Release phase but the release tail will not be cut off.

 ## AdsrEnvelope

An ADSR envelope controls the Attack, Decay, Sustain, and Release portions of a sound's volume. The Attack period is first, where the sound goes from silence to full volume. The Decay period is next, where the sound goes from full volume to its sustain volume. The Sustain period controls how long it stays at the sustain volume, and the Release period is where it goes from the sustain volume back to silence. The [ AdsrEnvelope ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/adsrenvelope.markdown) object used by the Zero Engine also has a parameter for delaying when the sound starts.

NOTE: Setting the `SustainTime` property to `0` will make the harmonic play indefinitely until the `NoteOff` method is called.

---
 # Related Materials

 ## Manual
- [soudnode_overview](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundnode/soudnode_overview.markdown)
- [MIDI ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundnode/midi.markdown)

 ## Code Reference
- [ AdditiveSynthNode ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/additivesynthnode.markdown)
- [ AdsrEnvelope ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/adsrenvelope.markdown) 

 