The [ DelayNode ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/delaynode.markdown) collects audio data from all of its inputs and applies a delay filter before passing it off to its outputs. 

 # Common Uses

- Using the `FeedbackPercent` property to create echo effects
- Combining with other audio filters to create sound effects

 # Using the DelayNode

The delay filter plays a second copy of the audio which is delayed by the number of seconds set by the `Delay` parameter. The `FeedbackPercent` property sets a percentage of the filter output which is fed back into the filter as input. If the `FeedbackPercent` is `0`, the user will only hear one repeat of the sound. If it was `100`, the sound would keep repeating indefinitely. Values in between will make each echo quieter than the last.

The `WetPercent` property controls the loudness of the delayed echo. At `100` the echo will sound just as loud as the original sound. Lower values will make the echo quieter than the sound.

---
 # Related Materials
 ## Manual
- [soudnode_overview](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/audio/soundnode/soudnode_overview.markdown)

 ## Code Reference
- [ DelayNode ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/delaynode.markdown) 

 