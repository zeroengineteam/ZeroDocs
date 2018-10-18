The [ HighPassNode ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/highpassnode.markdown) collects audio data from all of its inputs and applies a high pass filter to it before passing it along to its outputs. 

 # Common Uses

- Removing excessive low frequencies
- Combining with white noise and other audio filters to create wind or other sound effects

 # Using the HighPassNode

High pass filters leave high frequencies untouched while silencing low frequencies below their cutoff frequency. The only property on the HighPassNode is the `CutoffFrequency`, which sets the frequency at which the filter starts to take effect.

___
 # Related Materials
 ## Manual
- [soudnode_overview](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundnode/soudnode_overview.markdown)
- [bandpassnode](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundnode/bandpassnode.markdown)
- [lowpassnode](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundnode/lowpassnode.markdown)

 ## Code Reference
- [ HighPassNode ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/highpassnode.markdown) 

 