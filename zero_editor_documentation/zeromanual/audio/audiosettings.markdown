The [ AudioSettings ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/audiosettings.markdown) component can be added to Zero Engine's project settings to control project-wide audio settings. Some of these settings are advanced and must be used with caution.

 # Using the AudioSettings Component

 ## Volume

SystemVolume  is used to change the volume of audio produced by the Zero Engine. This volume modifier will be applied to all audio, both in the editor and during gameplay. This value can also be changed in the Volume Meter window or by using the `Audio.SetSystemVolume` and `Audio.GetSystemVolume` methods at runtime.

 ## Audio Channels

The MixType enum property allows the user to choose how many audio channels will be used when creating audio. The default setting, `AutoDetect`, will produce audio using the same number of channels as the user's default audio output device. Choosing any other setting will create audio using the specified number of channels which will then be automatically translated to match the number of channels needed by the audio output device. In most situations it is best to leave this setting on `AutoDetect`.

 ## Volume Threshold

The MinVolumeThreshold  property should also usually be left alone. Any sounds at a volume lower than this value will skip a significant portion of their processing. The sounds will continue to track their position and other relevant data, but will not output any audio data until their volume rises above this threshold. Raising this value can improve audio performance in some situations, but raising it too high will cause audible problems.

 ## Audio Latency

If the user is experiencing audio problems such as clicks, static, or other audible glitches, changing the LatencySetting enum to `High` could help. This will likely cause some perceptible audio lag, so it should only be used when necessary. This property can also be set by using the `Audio.SetUseHighLatency` method at runtime.

---
 # Related Materials

 ## Reference

- [ AudioSettings ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/code_reference/class_reference/audiosettings.markdown) 
  
  
  
  
  
  
  

 