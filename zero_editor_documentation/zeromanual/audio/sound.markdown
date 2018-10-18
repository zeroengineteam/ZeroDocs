A [ Sound ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/sound.markdown) resource is created for every imported audio file. Sounds can be attached to any number of [SoundCues](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundcue.markdown), allowing the user to play the same sound multiple ways while only storing the file once.

 # Using Sounds

 ## Supported Audio Formats

The Zero Engine supports audio files in both PCM WAV format (16 or 24 bit) and Ogg format, with up to eight audio channels, at almost any sample rate. (Note that audio output is usually at a sample rate of 44100 Hz or 48000 Hz, depending on the computer's output device, so it is best to use audio files with similar sample rates.) 

 ## Importing Audio Files

The easiest way to import audio files is to drag them directly onto a level. The Add window can also be used to choose the audio file. Both of these methods will then open a window with options for creating a SoundCue that will contain this Sound resource.

Once files are imported, they will be resampled to 48000 Hz and stored in a custom format using the Opus codec. Opus is a high-quality, low-latency compression format which can be quickly decoded at runtime. Using this format has little to no effect on what the user hears and significantly reduces the size of the project's audio.

 # SoundBuilder Options

When a Sound resource is selected, the [ SoundBuilder ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundbuilder.markdown) properties will be shown in the Property window.

NOTE: When changing these properties for an existing resource the user must click on the Reload button before the settings will take effect.

 ## Streaming Files
 ![SoundBuilder](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/85541.png)

When the Streamed checkBox property is un-checked the entire audio file is loaded into memory as soon as the resource is loaded. This simplifies the audio decoding, as all the data is stored and only decoded once. If Streamed checkBox is checked only a small piece of the file will be held in memory at any one time; these pieces will be repeatedly read from the disk as needed to play the file. This means that audio decoding will be happening continuously and repeatedly. Streaming files can negatively affect performance in some cases since they are repeatedly reading from disk while playing. 

In general the only audio that should be streamed are long files, such as background music, and only when worried about memory usage.

NOTE: Streaming files can’t be played multiple times simultaneously, can’t have their playback position set directly, and can’t use the LoopTailLength  property on [SoundEntries](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundcue.markdown#soundentries).

 ##  Normalizing
 ![SoundBuilder2](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/85543.png)

If the Normalize checkBox property is checked the MaxVolume  property will be shown and the volume of the audio file will be adjusted when it is processed and encoded. The volume of the entire audio file will be changed equally so that the highest volume peak will match the MaxVolume  property value. This can be used to either raise or lower the volume of an audio file.

---
 # Related Materials

 ## Manual

- [SoundCue ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundcue.markdown)
- [SoundEntry ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundcue.markdown#soundentries)

 ## Reference
- [ Sound ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/sound.markdown)
- [ SoundBuilder ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/soundbuilder.markdown) 

 