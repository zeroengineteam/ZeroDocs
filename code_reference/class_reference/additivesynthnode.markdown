 `Sound`

(NOTE) Generates audio using additive synthesis.

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ AddHarmonic](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/additivesynthnode.markdown#addharmonic-void)| |[soundnode](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/soundnode.markdown)| |
|[ NoteOff](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/additivesynthnode.markdown#noteoff-void)| | | |
|[ NoteOn](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/additivesynthnode.markdown#noteon-void)| | | |
|[ RemoveAllHarmonics](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/additivesynthnode.markdown#removeallharmonics-void)| | | |
|[ StopAllNotes](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/additivesynthnode.markdown#stopallnotes-void)| | | |


 #  Properties


---  
 #  Methods


---  
 #  AddHarmonic : Void

> Adds a new harmonic to the additive synth notes. The first value is the multiplier that will be applied to the base frequency, the second is the volume of this harmonic, and the third (the AdsrEnvelope object) contains the envelope-related values.
> |Name|Type|Description|
> |---|---|---|
> |frequencyMultiplier|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |volume|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |envelope|[adsrenvelope](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/adsrenvelope.markdown)| |
> |type|[SynthWaveType](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#synthwavetype)| |
> ``` lang=cpp, name=Zilch
> function AddHarmonic(frequencyMultiplier : Real, volume : Real, envelope : AdsrEnvelope, type : SynthWaveType)
> ``` 


---  
 #  NoteOff : Void

> Stops playing all current notes at the specified MIDI value.
> |Name|Type|Description|
> |---|---|---|
> |midiNote|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function NoteOff(midiNote : Real)
> ``` 


---  
 #  NoteOn : Void

> Starts playing a new note. The first parameter is the MIDI note value (range is 0 to 127), and the second is the volume modification that should be applied to this note (a value of 1.0 does not change the volume, while 0.0 would be silence).
> |Name|Type|Description|
> |---|---|---|
> |midiNote|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> |volume|[real](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/real.markdown)| |
> ``` lang=cpp, name=Zilch
> function NoteOn(midiNote : Real, volume : Real)
> ``` 


---  
 #  RemoveAllHarmonics : Void

> Removes all current harmonics. You must add at least one harmonic before playing a note.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function RemoveAllHarmonics()
> ``` 


---  
 #  StopAllNotes : Void

> Stops playing all current notes.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function StopAllNotes()
> ``` 


---  
 

 