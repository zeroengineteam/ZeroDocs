The [ VolumeNode ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/volumenode.markdown) collects audio data from all of its inputs and applies a volume modification to the samples before passing them off to its output nodes.

 # Common Uses

- Collecting several sounds together and changing their volume all at once

 # Using the VolumeNode

There are two linked properties that can be used to set the value of the volume modification: changing one of them will also change the value of the other. The `Volume` property is a floating point multiplier applied to the audio signal: a value of `1.0` does not affect the sound, `2.0` will double the volume, `0.5` will halve it, and `0.0` will make the sound inaudible. The `Decibels` property allows you to set the volume using the logarithmic decibel scale. A value of `0` dB does not affect the sound, `6` dB will double the sound’s volume, `-6` dB will halve it, and `-100` dB is effectively the same as setting Volume to `0`.

The volume can be interpolated over time using either floating point or decibel values with the `InterpolateVolume` and `InterpolateDecibels` methods. In both methods, the first value is the volume you want to interpolate to, and the second is the length of time (in seconds) for the interpolation. Using these methods ensures that the volume change is applied smoothly by the audio engine.

NOTE: If a VolumeNode has an output connection, setting the volume directly using the `Volume` or `Decibels` property is not actually instantaneous, so setting the volume and then calling `InterpolateVolume` immediately afterward may have unexpected results.

 ## Events

The `AudioInterpolationDone` event will be sent when a volume interpolation has finished.

---
 # Related Materials
 ## Manual
- [soudnode_overview](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundnode/soudnode_overview.markdown)

 ## Code Reference
- [ VolumeNode ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/volumenode.markdown) 

 