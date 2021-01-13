---
title: FAQ
date: '2018-07-07T09:53:27.000Z'
draft: false
weight: 1000
helpTitle: true
toc: true
description: Frequently Asked Questions
---

# FAQ

## I like JJazzLab and want to keep it free, how can I help? <a id="how-to-help"></a>

* Help [translate ](contribute/translate-jjazzlab/)JJazzLab
* [Contribute ](contribute/improve-doc.md)to improve this documentation
* Like the videos and subscribe the [YouTube channel](https://www.youtube.com/channel/UC0L3SwjY6bhTj6jsbOYzzAw)
* Record a video of yourself playing along with JJazzLab: videos will be put on the JJazzLab YouTube channel
* Spread the word ! Talk and add links to **www.jjazzlab.com** on social networks, blogs, websites, etc.
* If you're a developer, [contribute code](https://github.com/jjazzboss/JJazzLab-X/blob/master/CONTRIBUTING.md)

## I use MacOS, I can't find menu **Tools/Options?**

On MacOS the **Options** are accessed via the main menu **JJazzLab/Preferences**.

## How do I transpose a song? <a id="how-to-transpose-song"></a>

1. Select all the chord symbols \(right-click menu **Select all the chord symbols**\)
2. Use the mouse-wheel, or right-click menu **Transpose**

## How to generate an audio file \(.mp3, .wav, etc.\) from a JJazzLab backing track? <a id="generate-mp3"></a>

{% tabs %}
{% tab title="Windows" %}
It's easy if you use **VirtualMidiSynth** with the [JJazzLab SoundFont](configuration/jjazzlab-soundfont/):

1. in JJazzLab, save the backing tracks as a .mid file using menu **File/Export to Midi file**
2. open **VirtualMIDISynth** \(right-click from the icon in the Windows system tray\) and select the **MIDI converter**. Select the .mid file and generate the audio file.

You can also use a screen recorder software: some of them directly capture the output of the computer sound card and save it to a .mp3 file.
{% endtab %}

{% tab title="Linux" %}
Use the **FluidSynth -F** option to generate a .wav file.
{% endtab %}

{% tab title="VST Instruments" %}
Use the VST host \(Cubase, Reaper, etc.\) capabilities to record the output of the VST instruments.
{% endtab %}
{% endtabs %}

## How to force a clean re-installation?

You need to reset all JJazzLab user settings \(uninstall/re-install is not enough\). 

The simple way: menu **Tools/Options/Advanced,** button **Reset all user settings**.

The hard way: find the location of your **Netbeans user dir.** in menu **Help/About/System Information**, ****exit JJazzLab, then delete the **Netbeans user dir**.

## I don't have administration privileges on my Windows computer, can I install JJazzLab?

Yes. When first prompted by the JJazzLab installer, select "Install only for me", then select an installation directory where you have write access \(in My Documents for example\).

## I have a Yamaha arranger keyboard \(Tyros, PSR, ...\), how can I use it with JJazzLab?

JJazzLab can drive your keyboard to benefit from its optimized sounds. Connect your keyboard via Midi and go to the [**Output synth editor**](configuration/output-synth.md) and apply the **Yamaha Tyros** preset. This preset is based on Tyros5 which is backwards compatible with previous Tyros models and most of the PSR keyboards.

## How to make fonts bigger? <a id="font-bigger"></a>

In the JJazzLab installation directory, edit the file **etc/jjazzlab.conf** and add **--fontsize 16** \(16 or any other value, default is 11\) in the **default\_options** variable, you should end up with something like this:

`default_options="--branding jjazzlab -J-Djjazzlab.version=2.2.0 -J-Dplugin.manager.check.new.plugins=true -J-Dplugin.manager.check.interval=EVERY_DAY -J-DNOT_RUN_FROM_IDE=true --fontsize 16"` 

Restart JJazzLab. All menus should look bigger now.

This won't solve everything though, as some editor fonts do not depend on this setting. But you can tweak some of them using menu **Tools/Options/Theme**. Check each item in the list and if there is a font defined, change it to make it bigger. The user settings are automatically saved, so you need to do this only once.

## How to submit a bug? How to find the "log" file?

Send an [email ](https://www.jjazzlab.com/en/contact/)or, if you're a GitHub user, create an [issue](https://github.com/jjazzboss/JJazzLab-X/issues).

We need the following information in order to help you:

* Provide the content of the **log file** 
* Describe what does not work as expected
* Describe the sequence of actions that caused the issue

{% hint style="info" %}
A new **log file** is created upon each start of JJazzLab. It's important to get the right log file when the problem occured.
{% endhint %}

To get the log file content:

1. Right after the problem has occured, go to menu **Tools/Options/Advanced**
2. Click on **Show Log Window**
3. Copy & paste **the full content** of this window in your bug report

If for some reason the above does not work:

1. Go to menu **Help/About** and find the location of your **Netbeans user dir**.  For ex. on Windows `C:\Users\MyName\AppData\Roaming\jjazzlab\2.2` For ex. on Linux `/home/MyName/.jjazzlab/2.2`
2. Open an explorer, go to this directory then to the **var/log** subdirectory
3. The last log file is **messages.log**, the previous one is **messages.log.1**, the before previous is **messages.log.2**, etc.
4. Find the relevant log file and send it with your bug report

{% hint style="danger" %}
If you can't find the **Netbeans user dir**., make sure your explorer shows the hidden files \(e.g. the AppData directory is usually hidden on Windows\)
{% endhint %}



