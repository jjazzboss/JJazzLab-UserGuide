# Exporting songs

The exported file takes into account the current playback configuration:

* [Output synth](../sounds/other-synths.md) configuration
* [Mix console](../editors/mix-console.md) settings such as track's instrument, volume, mute state, etc.
* [Precount, click and tempo ](../playback-control/commands.md)settings
* The [playback key transposition](../tools/chord-symbols-transposition.md) settings

## Export to Midi

You can export a whole song to Midi via the menu **File/Export to Midi file...**&#x20;

You can also export individual tracks by [mouse-dragging from the Mix console](../editors/mix-console.md#export-to-midi-file-with-mouse-drag-and-drop).

#### Midi file format

Exported file is a multi-track type 1 Midi file.&#x20;

Each instrument track (from track 1) is initialized using the corresponding mix console track setting. Track 0 contains:

* If required, GM/GM2/GS/XG Midi initialization messages (depends on the output synth configuration)
* Tempo and time signature events
* Markers for chord symbols

## Export to audio

You can export the whole song to a **.wav** or **.mp3** file via menu **File/Export to Audio file...**

{% hint style="danger" %}
Audio export is only available if you use the internal [Fluidsynth output synth](../sounds/using-fluidsynth.md).
{% endhint %}

Check the **Separate tracks** option to export one audio file per track, as shown below.

<figure><img src="../.gitbook/assets/2024-12-06 18_39_56-Export to audio file.png" alt=""><figcaption></figcaption></figure>





