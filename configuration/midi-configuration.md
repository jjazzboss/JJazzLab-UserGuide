# Midi configuration

{% hint style="success" %}
If you don't want to mess with Midi, use the [JJazzLab SoundFont](jjazzlab-soundfont.md): it's optimized for JJazzLab and Yamaha styles, with the best compromise Sound quality Vs Ease of set up.
{% endhint %}

## Overview

![](../.gitbook/assets/midiwizard-image1.png)

JJazzLab is a Midi application. It does not directly generate audio output, rather it generates Midi messages \(eg “play a D on the bass”\) which are sent via the **Midi out device** to your **output synth**. 

The **Midi out device** can be selected in the menu **Tools/Options/Midi**.

The **output synth** produces the sounds. If JJazzLab knows the capabilities of your **output synth**, JJazzLab can directly control it from the **mix console.** And most importantly when you select a rhythm JJazzLab can automatically select the relevant sounds, using drum map conversion when necessary. 

Visit the [output synth](output-synth.md) page for more information.

## Midi Configuration Wizard <a id="midi-configuration-wizard"></a>

This wizard will help you select the best Midi configuration.  It is launched automatically the first time you run JJazzLab. You can also run it manually from the menu **Tools/Midi Configuration Wizard**.

## GM drums issues <a id="GM-drums-issue"></a>

A GM-only compatible output synth normally accepts drums/percussion data _only_ on channel 10. What if the JJazzLab song needs more than one drums channel ?

This typically happens for rhythms which have a drum track on channel 10 and another percussion track \(say channel 9\). This also happens if a song uses 2 different rhythms. Note that this should never happen if you [use the JJazzLab SoundFont](https://www.jjazzlab.com/en/doc/jjazzlab-soundfont).

The consequence is that when you play the song you hear strange repetitive sounds. For example because JJazzLab sends percussion data on channel 9 while the sound engine has a piano sound on channel 9.

So what can be done ?

* If your synth can handle several drum channels, use the [Output Synth Editor](https://www.jjazzlab.com/en/doc/output-synth-editor) to tell JJazzLab how to use this capability 
* Enable the Drums rerouting option JJazzLab can reroute non channel-10 drums/percussion tracks to channel 10. JJazzLab will automatically propose to activate this option upon playback if it detects a potential problem. The option can also be manually activated in the settings dialog of each drums-type channel in the Mix Console, as shown below.  ![](../.gitbook/assets/channelsettings.png)   



