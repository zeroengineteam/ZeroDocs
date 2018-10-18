The [ ModulationNode ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/modulationnode.markdown) collects audio data from all of its inputs and applies either amplitude or ring modulation to the audio before passing it along to its outputs. 

 # Common Uses

- Using amplitude modulation to regularly vary the volume of a sound
- Using ring modulation to create sound effects or synthesizers

 # Using the ModulationNode

Amplitude modulation will oscillate the volume of the audio at a rate set by the `Frequency` property. The volume changes from `0` to `1.0`. If the user does not want the volume to go to silence, setting the `WetPercent` to values below `100` will reduce the strength of the modulation.

Ring modulation will directly alter the frequencies of the sound, with stronger effects as the `Frequency` value gets larger.

---
 # Related Materials
 ## Manual
- [soudnode_overview](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundnode/soudnode_overview.markdown)

 ## Code Reference
- [ ModulationNode ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/modulationnode.markdown) 

 