# Midi コンフィギュレーション

{% hint style="success" %}
If you don't want to mess with Midi, just use the [JJazzLab SoundFont](jjazzlab-soundfont/). 
{% endhint %}

## Overview

![](../.gitbook/assets/midiwizard-image1%20%282%29.png)

JJazzLab is a Midi application. It does not directly generate audio output, rather it generates Midi messages \(eg “play a D on the bass”\) which are sent via the **Midi out device** to your [**output synth**](output-synth.md). 

The **Midi out device** can be selected in the menu **Tools/Options/Midi**.

The **Midi out device** must be connected to an external hardware synth via a Midi or USB cable, or via a **virtual Midi port** for a software synth \(VST instruments, SoundFont players, etc\). There are free virtual Midi ports on the web, such as [LoopBe1 ](https://nerds.de/en/loopbe1.html)on Windows or [Virmidi ](https://alsa.opensrc.org/Virmidi)on Linux.

{% hint style="warning" %}
You don't need a **virtual Midi port** if you use the **VirtualMidiSynth** SoundFont player on Windows, because this application installs itself as a **Midi out device**.
{% endhint %}

The **output synth** produces the sounds. If JJazzLab knows the capabilities of your **output synth**, JJazzLab can directly control it from the [**mix console**](../songs/song-editors/mix-console.md)**.** And most importantly when you select a rhythm JJazzLab can automatically select the relevant sounds, using drum map conversion when necessary. 

## Midi Configuration Wizard <a id="midi-configuration-wizard"></a>

This wizard will help you select the best Midi configuration.  It is launched automatically the first time you run JJazzLab. You can also run it manually from menu **Tools/Midi Configuration Wizard**.

