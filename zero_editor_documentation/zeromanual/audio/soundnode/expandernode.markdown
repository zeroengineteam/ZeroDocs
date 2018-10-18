The [ ExpanderNode ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/expandernode.markdown) collects audio data from all of its inputs and applies an expander filter before passing the data along to its outputs. 

 # Common Uses

- Increasing the contrast between the soft and loud parts of the audio
- Removing quiet sounds from the audio

 # Using the ExpanderNode 

Expander filters reduce the volume of sounds that drop below the threshold, according to a specified ratio. The volume is calculated according to this formula:

(NOTE) VolumeAdjustmentDecibels = ((1.0 / Ratio) - 1.0) * (ThresholdDecibels - CurrentVolume)

In other words, if the `Ratio` is `2`, the `ThresholdDecibels` is `-10` dB, and the current volume of the sound is `-14` db, the volume adjustment will be `-2` dB and the sound will be reduced to `-16` db.  If the `Ratio` is set to `0.0`, the `(1.0 / Ratio) - 1.0` value will be set to `0.0`, so audio that goes below the `ThresholdDecibels` value will have their volume reduced by the same number of decibels that they are below the threshold. This will create an effect like a Gate filter.

The `AttackMillisec` and `ReleaseMillisec` properties control how quickly the filter eases in and out as the sound goes below the `ThresholdDecibels` then goes back above it. The `AttackMillisec` should generally be short and the `ReleaseMillisec` should be longer, but this will depend on the desired effect. The `KneeWidth` property sets the number of decibels, centered at the `ThresholdDecibels`, over which the volume change eases in. 

---
 # Related Materials
 ## Manual
- [soudnode_overview](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundnode/soudnode_overview.markdown)
- [compressornode](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundnode/compressornode.markdown)

 ## Code Reference
- [ ExpanderNode ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/expandernode.markdown) 

 