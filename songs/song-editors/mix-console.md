---
title: Mix Console
date: '2017-10-17T15:26:15.000Z'
draft: false
weight: 330
helpTitle: false
---

# Mix console

Use the **mix console** to:

* Change the instruments
* Adjust channel settings: volume, reverb, chorus, panoramic, transposition, velocity offset
* Mute or solo channels
* Load/save .mix file
* And more: change Midi channel, use special Midi commands, etc.

JJazzLab uses the **mix console** information to send the relevant Midi messages to the [output synth](../../configuration/output-synth.md). This is done each time you make a change in the mix console, or when you start the playback.

{% hint style="danger" %}
Midi has only 16 Midi channels**.** That's why usually a song can't have more than 2 rhythms.
{% endhint %}

![](../../.gitbook/assets/mixconsole.png)

## MIx console menu bar

### Menu File

* **Load/Save Default Rhythm Mix**  

  Change the current mix from a file. Consult [this page](../song-and-mix-files.md) for more information about .mix files.

* **Import Mix...**  

  Note that this will import settings only for the instruments which are common between the current mix and the imported mix.

### Menu Edit

* **Add/Remove user channel**   

  The user channel is used to automatically set the instrument that you want to play for a given song or rhythm.  

  _Example: you're a keyboardist and JJazzLab is connected to your synthesizer. You made Stevie Wonder's "Isn't she lovely" song and you play a clavinet sound on it. Add the User Channel with a Clavinet sound, increase the chorus effect, then save the song. This way, the next time you load the song you'll automatically get your clavinet sound recalled on your synthesizer._  

* **Reset channels**  

  Restore the original settings from the related rhythm.

### Menu Midi

* **Enable/Disable all Midi parameters**  

  Use Disable all Midi parameters if you control the mix yourself directly on the output synth.

* **Send GM/GM2/XG/GM mode ON message**  

  This lets you send special Midi initialization messages to turn your output synth in the desired mode.

## Change instrument

Click on the instrument name in the channel. Note that this is also where instrument transposition can be adjusted.

![](../../.gitbook/assets/mixconsole-instrumentselection.png)

## Channel settings

Use the channel settings to:

* **Add a Midi velocity offset to all notes played on this channel**  

  Note that this is slightly different from adjusting the volume.  

* **Disable sending specific Midi messages**  

  Probably because you control the parameter yourself directly on the [output synth](../../configuration/output-synth.md).  

* **Use drums-rerouting for channels drums**  

  If you use a basic GM output synth, it can play drums **only on channel 10**. If drums/percussion are used on other channels in your mix,  you need to activate drums rerouting on these channels. Note that JJazzLab may activate this option for you if it detects, based on the current [output synth](../../configuration/output-synth.md) information, potential issues.   

![](../../.gitbook/assets/mixconsole-channelsettings.png)

## Midi channel

Each Midi channel can be changed manually.

![](../../.gitbook/assets/mixconsole-changechannel%20%281%29.png)

## Multi-rhythm songs

When a song uses 2 or more rhythms, a popup is displayed in the upper left corner of the mix console to select the rhythm you want to display.

![](../../.gitbook/assets/mixconsole-rhythmselectionpopup.png)

Note that some commands such as menu **Edit/Reset channels** will not be applied to the hidden rhythm\(s\).

## Mouse shortcuts

| Selection | Mouse | Action |
| :--- | :--- | :--- |
| channel volume slider, knobs | double-click | Input value with keyboard |
| channel volume slider | shift-drag | change volume of all channels |

