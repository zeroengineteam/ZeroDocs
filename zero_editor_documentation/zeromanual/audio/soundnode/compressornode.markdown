The [ CompressorNode ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/compressornode.markdown) collects audio data from all of its inputs and applies a compressor filter before passing the data along to its outputs. 

 # Common Uses

- Preventing a sound (or group of sounds) from becoming too loud

 # Using the CompressorNode 

Compressor filters reduce the volume of sounds that go above a certain threshold, according to a specified ratio. The volume is calculated according to this formula:

(NOTE) VolumeAdjustmentDecibels = (1.0 - (1.0 / Ratio)) * (ThresholdDecibels - CurrentVolume)

In other words, if the `Ratio` is `4.0`, the `ThresholdDecibels` is `-2` dB, and the current volume of the sound is `+2` db, a volume adjustment of `-3` dB will be applied and the volume of the sound will be reduced to `-1` dB. If the `Ratio` property is set to `0.0`, the `1.0 - (1.0 / Ratio)` value will be set to `1.0`, so the volume will never go above the `ThresholdDecibels` value: this creates a Limiter filter.

The `AttackMillisec` and `ReleaseMillisec` properties control how quickly the filter eases in and out as the sound goes above the `ThresholdDecibels` then goes back below. The `AttackMillisec` should generally be short and the `ReleaseMillisec` should be longer, but this will depend on the desired effect. The `KneeWidth` property sets the number of decibels, centered at the `ThresholdDecibels`, over which the volume compression eases in. 

---
 # Related Materials
 ## Manual
- [soudnode_overview](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundnode/soudnode_overview.markdown)
- [expandernode](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundnode/expandernode.markdown)

 ## Code Reference
- [ CompressorNode ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/compressornode.markdown) 

 