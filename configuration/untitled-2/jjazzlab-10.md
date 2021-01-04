# JJazzLab

Use the **Mix Console** to:

* Change the instruments
* Adjust volume, reverb, chorus, pan., transposition per channel
* Mute or solo channels
* Load/save .mix file \(Mix Console configuration\)
* And more: change Midi channel, use special Midi commands, etc.

JJazzLab uses the Mix Console information to send the relevant Midi messages to the output synth. This is done each time you make a change in the Mix Console or when you start the playback.

**Midi has only 16 Midi channels!** That’s why usually a song can’t have more than 2 rhythms.

Menu FILE

* **Load/Save Default Rhythm Mix**  Change the current mix from a file. Consult [this page](https://www.jjazzlab.com/en/doc/song-and-mix-files) for more information about .mix files.
* **Import Mix…**  Note that this will import settings only for the instruments which are common to the current mix and the imported mix.

Menu EDIT

* **Add/Remove user channel**  The user channel is used to automatically set the instrument that _you_ want to play for a given song or rhythm.  _Example: you’re a keyboardist and JJazzLab is connected to your synthesizer. You made Stevie Wonder’s “Isn’t she lovely” song and you play a clavinet sound on it. Add the User Channel with a Clavinet sound, increase the chorus effect, then save the song. This way, the next time you load the song you’ll automatically get your clavinet sound recalled on your synthesizer._
* **Reset channels**  Restore the original settings from the related rhythm.

Menu MIDI

* **Enable/Disable all Midi parameters**  Use Disable all Midi parameters if you control the mix yourself directly on the output synth.
* **Send GM/GM2/XG/GM mode ON message**  This lets you send special Midi initialization messages to turn your output synth in the desired mode.

## Change instrument <a id="change-instrument"></a>

Click on the instrument name in the channel. Note that this is also where instrument transposition can be adjusted.

## Channel settings <a id="channel-settings"></a>

Use the channel settings to:

* **Add a Midi velocity offset to all notes played on this channel**  Note that this is slightly different from adjusting the volume.
* **Disable sending specific Midi messages**  Probably because you control the parameter yourself directly on the output synth.
* **Use drums-rerouting for channels drums**  If you use a basic GM output synth \(see [here](https://www.jjazzlab.com/en/doc/midi-configuration#GM-drums-issue) for more info\). This is usually handled automatically by JJazzLab in relation with the output synth configuration.

## Midi channel <a id="midi-channel"></a>

Each Midi channel can be changed manually.

## Multi-rhythm songs <a id="multi-rhythm-songs"></a>

When a song uses 2 or more rhythms, a popup is displayed in the upper left corner of the Mix Console to select the rhythm you want to display.

Note that some commands such as menu Edit/Reset channels will not be applied to the hidden rhythm\(s\).

## Mouse shortcuts <a id="mouse-shortcuts"></a>

| Selection | Mouse | Action |
| :--- | :--- | :--- |
| Channel volume        | shift-drag        | change the volume of _all_ channels in the same time |

