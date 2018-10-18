The [ RecordingNode ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/recordingnode.markdown) collects audio data from its inputs and writes that data to a file. The audio data is then passed along to its outputs with no changes. 

 # Common Uses

- Allowing the player to record game audio
- Saving sound effects or music created in the Zero Engine

 # Using the RecordingNode

The file created by the RecordingNode will be in WAV format. By default the node will constantly write small amounts of data to the file (when `StreamToDisk` is True). The disk access will not affect the audio, but it could possibly affect the game performance. The RecordingNode can also save all data into a buffer and write it all at once when recording is stopped. Unless the recording is very short, writing this much data to disk at once will take a noticeable amount of time. Which method to choose depends on usage and performance needs.

IMPORTANT: The `FileName` must contain the full path of the location where the file should be opened and all folders in the path must already exist. Do NOT include a file extension. This property must be set before calling `StartRecording`.

The following code shows how to create a file named "RecordingTest.wav" inside the Zero folder in the user's Documents folder.
```lang=csharp
this.MyRecorder.FileName = FilePath.CombineDirectoriesAndFile(FilePath.UserDocumentsDirectory, "Zero\\", "RecordingTest");
```

---
 # Related Materials
 ## Manual
- [soudnode_overview](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundnode/soudnode_overview.markdown)

 ## Code Reference
- [ RecordingNode ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/recordingnode.markdown) 

 