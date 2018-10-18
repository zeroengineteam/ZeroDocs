If a MIDI device is connected when the Zero Engine starts up it will listen for messages from that device and send corresponding [ MidiEvents ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/midievent.markdown). It does not keep track of device changes, so if a MIDI keyboard is plugged in after the editor or the game is running it won't respond to that device.

 # Common Uses

- Using a synthesizer created with the [AdditiveSynthNode ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundnode/additivesynthnode.markdown)
- Alternate game input and control 

 # Using the MIDI Events

Each `MidiEvent` has three properties, though not all of them apply to every event. See the table below for the property meanings on each type of event.
- The `Channel` property is the MIDI channel received from the device.
- The `MIDINumber` property is the MIDI note number associated with the message. This value will be 0 on event types where it is not applicable.
- The `Value` property contains the value, if any, that was associated with the MIDI message. Most of these values will be integers from 0 to 127 and will need to be translated before they are used. This value will be 0 on event types where it is not applicable.

The following events will be sent whenever a corresponding MIDI message is received from the connected device:

- MIDINoteOn: sent whenever a note should start playing, i.e. when a key is pressed on a keyboard. 
- MIDINoteOff: sent when a note should stop playing, i.e. when a key is released on a keyboard. (Some MIDI devices will send a NoteOn message with a volume of 0 instead of a NoteOff message.)
- MIDIVolume: sent when an overall volume control is changed on the MIDI device. 
- MIDIPitchWheel: sent when the pitch control is changed on the MIDI device.
- MIDIModWheel: sent when the modulation control is changed on the MIDI device.
- MIDIOtherControl: sent for all other control change messages received from the MIDI device.


| Event Type | Channel   | MIDINumber  | Value 
| ---- | ---- | ---- | ----
| MIDINoteOn | Channel# | Note# | Volume of the note in the range 0 - 127. Should be translated to 0.0 - 1.0.
| MIDINoteOff | Channel# | Note# | N/A
| MIDIVolume | Channel# | N/A | Volume set by the device in the range 0 - 127. Should be translated to 0.0 - 1.0.
| MIDIPitchWheel | Channel# | N/A | Pitch set by the device in the range -1.0 - 1.0.
| MIDIModWheel | Channel# | N/A | Modulation value in the range 0 - 127.
| MIDIOtherControl | Channel# | Control# | Control value in the range 0 - 127.

---
 # Related Materials

 ## Manual

- [AdditiveSynthNode ](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/audio/soundnode/additivesynthnode.markdown)

 ## Reference

- [ MIDIEvent ](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/midievent.markdown) 

 