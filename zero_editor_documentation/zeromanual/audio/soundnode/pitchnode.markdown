The [ PitchNode ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/pitchnode.markdown) collects audio data from all of its inputs and applies a pitch modification to the samples before passing them off to its output nodes.

 # Common Uses

- Controlling the pitch of several sounds at once

 # Using the PitchNode

WARNING: When using PitchNodes, if a generating node has multiple output connections the user must make sure all of them are at the same pitch. If SoundNodes request data from the generating node at different pitch settings there will be an error and the nodes will be disconnected.

 ## Pitch and Semitones

PitchNodes have two linked properties for setting their pitch change: changing one will also change the value of the other. Raising the pitch also speeds up the sound, while lowering the pitch slows it down. Large pitch changes will likely affect the quality of the sound.

The `Pitch` property is a floating point value where `0.0` does not affect the pitch, `1.0` raises the pitch by an octave (doubles the pitch), `2.0` raises it by two octaves, `-1.0` lowers it by an octave, etc. The Semitones property uses semitone (or half-step) values to set the pitch. There are twelve semitones in an octave, so a value of `12` would double the pitch while `-12` would halve it.

The pitch can be interpolated over time using either floating point or semitone values with the `InterpolatePitch` and `InterpolateSemitones` methods. In both methods, the first value is the pitch to interpolate to, and the second is the length of time (in seconds) for the interpolation. Using these methods ensures that the pitch change is applied smoothly by the audio engine.

 ## Events

The `AudioInterpolationDone` event will be sent when a pitch interpolation has finished.

---
 # Related Materials
 ## Manual
- [soudnode_overview](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundnode/soudnode_overview.markdown)

 ## Code Reference
- [ PitchNode ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/pitchnode.markdown) 

 