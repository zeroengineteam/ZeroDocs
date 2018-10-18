The [ ReverbNode ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/reverbnode.markdown) collects audio data from all its inputs and applies a simple reverb filter before passing it off to its outputs. 

 # Common Uses

- Creating an echoing ambience for areas such as large rooms or caves

 # Using the ReverbNode

Although ReverbNodes use relatively straightforward calculations, they do take computation time. It is best to use as few ReverbNodes as possible. Reverb calculations will not affect game performance, but if they take too long, it will result in audio glitches. Any reverb that is not dependent on factors that change during gameplay should be applied to the audio files themselves using higher-quality reverb in audio software.

The `Length` property sets the length of the reverb tail (the number of seconds it will take for a sound to completely die away after it finishes playing). The `WetPercent` property controls the percentage of the audio which is affected by the reverb filter. This can be smoothly changed over time using the `InterpolateWetPercent` method.

---
 # Related Materials
 ## Manual
- [soudnode_overview](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundnode/soudnode_overview.markdown)

 ## Code Reference
- [ ReverbNode ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/reverbnode.markdown) 

 