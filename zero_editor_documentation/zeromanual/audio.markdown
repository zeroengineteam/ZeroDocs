
 # [Sound ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/sound.markdown)

A Sound resource is created for every imported audio file. Sounds can be attached to any number of SoundCues, allowing the user to play the same sound multiple ways while only storing the file once.

 # [SoundCue ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundcue.markdown)

SoundCues are a fundamental part of playing audio in the Zero Engine, allowing the user to modify various properties without affecting the original Sound resource.

 # [SimpleSound ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/simplesound.markdown)

The SimpleSound component, like its name suggests, is a simple way to play a sound, requiring only a SoundEmitter component and a SoundCue.

 # [SoundAttenuator ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundattenuator.markdown)

The SoundAttenuator resource controls how a sound played through a SoundEmitter on an object decreases in volume as the object gets further away from a SoundListener.

 # [SoundEmitter ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundemitter.markdown)

The SoundEmitter component handles the 3D positioning of sounds in a level. 

 # [SoundInstance ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundinstance.markdown)

SoundInstances are created at runtime whenever a SoundCue is played, and can then be controlled by the user in scripts.

 # [SoundListener ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundlistener.markdown)

The SoundListener component “hears” all positional audio in a SoundSpace.

 # [SoundSpace ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundspace.markdown)

The SoundSpace keeps sounds separate from other Spaces and allows the user to control overall settings for all audio in the SoundSpace.

 # [SoundTag ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundtag.markdown)

SoundTags are resources that allow users to pause, resume, and stop a group of SoundInstances; control their volume, EQ, and compression; and get a list of tagged SoundInstances to change other properties in ZilchScripts.

 # [Volume Meter ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/volume_meter.markdown)

The Volume Meter tool allows the user to monitor and change the audio system volume. 

 # [SoundNode ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundnode.markdown)

SoundNodes are the underlying objects which create and modify all audio in the Zero Engine. Many types of SoundNodes can only be created and added to the node graph in ZilchScripts.

 # [SoundNode Graph ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundnode_graph.markdown)

The SoundNode Graph tool displays the connections between all SoundNodes that are currently attached to the output of a SoundSpace. 

 # [MIDI ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/midi.markdown)

If a MIDI device is connected when the Zero Engine starts up it will listen for messages from that device and send corresponding MidiEvents. 

 # [AudioSettings ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/audiosettings.markdown)

The AudioSettings component can be added to Zero Engine's project settings to control project-wide audio settings. 

 