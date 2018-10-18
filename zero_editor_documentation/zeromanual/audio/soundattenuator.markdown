The [ SoundAttenuator ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundattenuator.markdown) resource controls how a sound played through a [SoundEmitter ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundemitter.markdown) on an object decreases in volume as the object gets further away from a  [SoundListener ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundlistener.markdown). 

 # Using SoundAttenuators 


![Attenuator1](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/3057.png)


SoundAttenuators can be added to both [SoundCues ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundcue.markdown) and SoundEmitters. If a SoundCue has a SoundAttenuator other than the DefaultNoAttenuation resource attenuator, its settings will be used when the SoundCue is played through any SoundEmitter. Otherwise the settings from the SoundAttenuator on the SoundEmitter will be used. If the SoundEmitter also has DefaultNoAttenuation resource selected, the sound will be heard spatially by SoundListeners (panned to left or right depending on the location of the object), but will not change its volume with distance.

 ## Attenuation

The volume of sounds are reduced, or attenuated, according to their distance from a relevant SoundListener, using a specified curve. In the real world, as sounds get further away their volume drops off quickly at first, and then slowly. This logarithmic curve is the default setting for SoundAttenuators, but other types of curves can be chosen for custom behaviors.

 ## Low Pass Filter



![Attenuator2](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/3059.png) Another thing that happens in the real world with distance is that high frequencies are attenuated more quickly than low frequencies. This can be imitated by applying a low-pass filter to the audio. The low-pass filter on SoundAttenuators can be turned off and on depending on the desired sound.


---
 # Related Materials

 ## Manual

- [SoundEmitter ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundemitter.markdown)
- [SoundListener ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundlistener.markdown)
- [SoundCue ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundcue.markdown)

 ## Reference

- [ SoundAttenuator ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundattenuator.markdown) 

 