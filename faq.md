---
description: Frequently Asked Questions
---

# FAQ

## I like JJazzLab and want to keep it free, how can I help? <a href="#how-to-help" id="how-to-help"></a>

* [Donate ](https://www.jjazzlab.com/en/donate/)to keep JJazzLab free for all
* Help [translate ](contribute/translate-jjazzlab/)JJazzLab
* [Contribute ](contribute/improve-doc.md)to improve this documentation
* Like the videos and subscribe the [YouTube channel](https://www.youtube.com/channel/UC0L3SwjY6bhTj6jsbOYzzAw)
* Record a video of yourself playing along with JJazzLab: videos will be put on the JJazzLab YouTube channel
* Spread the word ! Talk and add links to **www.jjazzlab.com** on social networks, blogs, websites, etc.
* If you're a developer, [contribute code](https://github.com/jjazzboss/JJazzLab-X/blob/master/CONTRIBUTING.md)

## I use MacOS, I can't find menu **Tools/Options?**

On MacOS the **Options** are accessed via the main menu **JJazzLab/Preferences**.

## How do I transpose a song? <a href="#how-to-transpose-song" id="how-to-transpose-song"></a>

1. Select all the chord symbols (right-click menu **Select all the chord symbols**)
2. Use the mouse-wheel, or right-click menu **Transpose**

## Can I use VST/AU plugins with JJazzLab?

Yes, but not directly because JJazzLab can not host VST plugins.&#x20;

1. Install a virtual midi device and a VST Host software on your computer. You'll find on the web free applications for Windows, Linux and Mac. For example use **loopMIDI** (we recommend to disable its _feedback detection_ in the _Advanced_ settings) and **SoundBridge** on Windows.
2. In JJazzLab, go to **Midi options** and set the **Midi out device** to **loopMIDI**
3. In your VST Host software, set the **Midi in device** to **loopMidi** and make sure the VST Host and the VST plugins are configured so that all Midi channels (1-16) are received.
4. Play a song in JJazzLab: you should hear the VST instruments
5. If you don't want to select the VST sounds directly from JJazzLab, you might want to _Disable all Midi parameters_ from the Midi menu in the Mix Console.

## How to generate an audio file (.mp3, .wav, etc.) from a JJazzLab backing track? <a href="#generate-mp3" id="generate-mp3"></a>

From JJazzLab 4, just use menu File/Export to audio.

## How to force a clean re-installation?

You need to reset all JJazzLab user settings (uninstall/re-install is not enough).

The simple way: menu **Tools/Options/Advanced,** button **Reset all user settings**.

The hard way: find the location of your **Netbeans user dir** in menu **Help/About/System Information**, **\*\*exit JJazzLab, then delete the** Netbeans user dir\*\*.

## I don't have administration privileges on my Windows computer, can I install JJazzLab?

Yes. When first prompted by the JJazzLab installer, select "Install only for me", then select an installation directory where you have write access (in My Documents for example).

## How to get better sounds?

From JJazzLab 4, the application embeds a ready-to-use software synth (FluidSynth) optimally configured for JJazzLab.

To get the best sounds, you'll need to use VST/AU plugins, see question above.

{% hint style="warning" %}
There is a free version of Halion Sonic SE from Steinberg which can be used with JJazzLab to get **really good** **sounding** backing tracks, more info on the [JJazzLab forum](https://jjazzlab.freeforums.net/thread/215/new-great-sounds-jjazzlab).
{% endhint %}

## I have a Yamaha arranger keyboard (Tyros, PSR, ...), how can I use it with JJazzLab?

JJazzLab can drive your keyboard to benefit from its optimized sounds.&#x20;

* Connect your keyboard via Midi
* Go to the Midi Out tab of Options/Preferences
* Select the Midi output connected to your synth
* In the Output Synth part, select **Add synth from file.**.., and choose **YamahaRefSynth.ins**.

## How to make fonts bigger? <a href="#font-bigger" id="font-bigger"></a>

In the JJazzLab installation directory, edit the file **etc/jjazzlab.conf** and add **--fontsize 16** (16 or any other value, default is 11) in the **default\_options** variable, you should end up with something like this:

`default_options="--branding jjazzlab -J-Djjazzlab.version=2.2.0 -J-Dplugin.manager.check.new.plugins=true -J-Dplugin.manager.check.interval=EVERY_DAY --fontsize 16"`

Restart JJazzLab. All menus should look bigger now.

This won't solve everything though, as some editor fonts do not depend on this setting. But you can tweak some of them using menu **Tools/Options/Theme**. Check each item in the list and if there is a font defined, change it to make it bigger. The user settings are automatically saved, so you need to do this only once.

{% hint style="info" %}
If you use 4K or 5K monitors, JJazzLab may look too small, with unreadable fonts. In this case add **-J-Dsun.java2d.uiScale=2** in the **default\_options** variable, like in the example above. JJazzLab will look twice as bigger.
{% endhint %}

## Can I start JJazzLab with command line arguments?

You can pass one or more .sng file names on the command line, JJazzLab will open them upon start.

```
# Example on Win10 (x64)
"C:\Program Files\JJazzLab\bin\jjazzlab64.exe" "C:\my dir\MySong.sng" "D:\AnotherSong.sng"
```

## How to submit a bug? How to find the "log" file?

Create a new thread in the [JJazzLab forum](https://jjazzlab.freeforums.net/) or, if you're a GitHub user, create an [issue](https://github.com/jjazzboss/JJazzLab-X/issues).

We need the following information in order to help you:

* Provide the content of the **log file**&#x20;
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
If you can't find the **Netbeans user dir**., make sure your explorer shows the hidden files (e.g. the AppData directory is usually hidden on Windows)
{% endhint %}
