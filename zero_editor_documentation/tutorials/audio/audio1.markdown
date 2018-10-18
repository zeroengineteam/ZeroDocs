This lesson focuses on covering the basics of audio in Zero Engine.

 # Learning Objectives

- Importing audio files
- Creating and playing sound cues

 # Level Setup

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#newproject)
 - Create a new project using the {nav icon=clone, name=Empty 2D Project} template
- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#createsprite)
- In the `Properties Window`
 - Rename Sprite object to `Square`
 - [Add Component](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/addremovecomponent/) : [RigidBody](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown)
 - [Add Component](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [ SoundEmitter](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundemitter.markdown)
 - [Add Component](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [ SimpleSound](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/simplesound.markdown)

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)



![AudioI](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46662.gif)


- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)

 # Importing Audio

In Zero Engine, you can play sound files by importing them as resources. There are two important resources to play audio; [Sound](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/sound.markdown) and [SoundCue](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundcue.markdown). By default, Zero Engine includes both a DefaultSound resource and a DefaultSoundCue resource resources, which is what we hear when running the game. Let's experiment by adding a new sound file.

- Download the following file:
 ![Buzz](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46672.wav)
- Import it into the project by dragging and dropping the file into the `Level Window`
- In the `Import Window`
 - Set GenerateCue  to `PerSound`
 - Set GroupName  to `Buzz`
 - Press the `Import All` button



![SoundImport](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46996.gif)


Now we have added both a Sound resource and SoundCue resource resource to our project. We can verify this by looking at the `Library Window` under the respective tags.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/88672.png)


NOTE: Zero Engine only supports `WAV` and `OGG` audio formats, if the file you are looking to import is of a different extension, you'll need it to convert it first.

 # Sound Cue

SoundCues are resources that allow you to modify properties of a sound without altering the sound files themselves and are necessary to play any kind of audio in Zero Engine. Let's take a look at a few of the SoundCue resource settings.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47005.png)


| Common Sound Cue Properties |
|------|
| PlayMode enum | Whether the sound should a [Single](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#soundplaymode) time or [loop](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#soundplaymode) on completion |
| Volume  & Decibels  | How quiet or loud the sound should be played |
| Pitch  & Semitones  | How high or low pitched the sound should be played |
| VolumeVariation  | Added random volume variation within the given range when sound is played |
| PitchVariation  | Added random pitch variation within the given range when sound is played |
| Attenuator enum | The resource that defines how the sound behaves based on distance from the origin |

- In the `Library Window`
 - Under the SoundCue  tag
  - `Double-Click` Buzz 
- In the `Properties Window`
 - Set PlayMode  to `Looping`
- [Select](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Square object
- In the `Properties Window`
 - Under [ SimpleSound](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/simplesound.markdown)
  - Set SoundCue enum to `Buzz`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)

You should now be hearing the Buzz  sound effect looping.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)

 # Attenuation

Previously, we have played sounds that remain just as loud irrespective of the emitter's position (non-positional sounds). Zero Engine also allows us to setup sounds to be played positionally; growing louder or quieter based on the [Sound Listener](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundlistener.markdown)'s position, which is added by default to the `Game Camera` object.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/88634.png)


Let's take a look on how to play positional sounds.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : 
 [Add Resource](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a SoundAttenuator resource named `CustomAttenuation`
- In the `Library Window`
 - Under SoundAttenuator 
  - `Double-Click` CustomAttenuation resource
- In the `Properties Window`
 - Set StartDistance  to `10`
 - Set StopDistance  to `50`
 - Set MinAttenuatedVolume  to `0`
- [Select](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : Square object
- In the `Properties Window`
 - Under [ SoundEmitter](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundemitter.markdown)
  - Set Attenuator  to `CustomAttenuation`
 - Under [ SimpleSound](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/simplesound.markdown)
  - Set Positional checkBox to `true`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)

If done correctly, you should notice the sound getting quieter as the Square object object falls and gets farther from the `Game Camera` which has a [SoundListener](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundlistener.markdown).

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)

 # Related Materials

 ## Manual
- {icon university}[[sound](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/sound.markdown)
- {icon university}[[soundcue](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundcue.markdown)
- {icon university}[[simplesound](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/simplesound.markdown)
- {icon university}[[soundattenuator](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundattenuator.markdown)
- {icon university}[[soundemitter](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundemitter.markdown)
- {icon university}[[soundlistener](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundlistener.markdown)

 ## Code Reference
 ### Classes
- [Sound](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/sound.markdown)
- [SoundCue](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundcue.markdown)
- [Transform](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/Transform.markdown)
- [SoundEmitter](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/SoundEmitter.markdown)
- [SimpleSound](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/SimpleSound.markdown)
- [SoundListener](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/SoundListener.markdown)
- [RigidBody](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/rigidbody.markdown)

 ### Commands
- [Create a New 2D Project](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#newproject)
- [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#add)
- [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)
- [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)
- [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#createsprite) 

 