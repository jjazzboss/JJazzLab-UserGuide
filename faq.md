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

1. Install a virtual midi device and a VST Host software on your computer. You'll find on the web free applications for Windows, Linux and Mac. For example use **loopMIDI** (we recommend to disable _feedback detection_ in the _Advanced_ settings) **** and **SoundBridge** on Windows.
2. In JJazzLab, go to **Midi options** and set the **Midi out device** to **loopMIDI**
3. In your VST Host software, set the **Midi in device** to **loopMidi** and make sure the VST Host and the VST plugins are configured so that all Midi channels (1-16) are received.
4. Play a song in JJazzLab: you should hear the VST instruments

## How to generate an audio file (.mp3, .wav, etc.) from a JJazzLab backing track? <a href="#generate-mp3" id="generate-mp3"></a>

{% tabs %}
{% tab title="Windows" %}
It's easy if you use **VirtualMidiSynth** with the [JJazzLab SoundFont](configuration/jjazzlab-soundfont/):

1. in JJazzLab, save the backing tracks as a .mid file using menu **File/Export to Midi file**
2. open **VirtualMIDISynth** (right-click from the icon in the Windows system tray) and select the **MIDI converter**. Select the .mid file and generate the audio file.

You can also use a screen recorder software: some of them directly capture the output of the computer sound card and save it to a .mp3 file.
{% endtab %}

{% tab title="Linux" %}
Use the **FluidSynth -F** option to generate a .wav file.
{% endtab %}

{% tab title="VST Instruments" %}
Use the VST host (Cubase, Reaper, etc.) capabilities to record the output of the VST instruments.
{% endtab %}
{% endtabs %}

## How to force a clean re-installation?

You need to reset all JJazzLab user settings (uninstall/re-install is not enough).

The simple way: menu **Tools/Options/Advanced,** button **Reset all user settings**.

The hard way: find the location of your **Netbeans user dir** in menu **Help/About/System Information**, **\*\*exit JJazzLab, then delete the** Netbeans user dir\*\*.

## I don't have administration privileges on my Windows computer, can I install JJazzLab?

Yes. When first prompted by the JJazzLab installer, select "Install only for me", then select an installation directory where you have write access (in My Documents for example).

## How to get better sounds?

{% hint style="warning" %}
May 2021 update: the new free version of Halion Sonic SE from Steinberg can be used with JJazzLab to get **really good** sounding backing tracks, more info on the [JJazzLab forum](https://jjazzlab.freeforums.net/thread/215/new-great-sounds-jjazzlab).
{% endhint %}

You need a _good synthesizer_ connected to the output of JJazzLab. But what means _good synthesizer_ when we talk about backing track generation? There are 3 main factors to take into account:

1. **Individual sound quality** (sounds for drums, bass, piano, ...)
2. **Overall sound mix**  (how the different instruments fit together)
3. **Effects** (overall and per-instrument effects)

{% hint style="info" %}
Experience shows that factors 2. and 3. can be as much important as factor 1.
{% endhint %}

2 other factors can also impact the backing track rendering :

* **Drums XG compatibility**: many Yamaha styles use specific XG drum/percussion sounds, e.g. jazz brushes, etc.
* **Correct Output Synth configuration in JJazzLab**: Yamaha styles define a preferred instrument (e.g. synth bass) for each channel. If the Output Synth configuration is wrong, JJazzLab can't select the optimal instrument for each channel (e.g. use a piano sound instead of a synth bass).

Below are some typical configurations.

| Output Synth                          | Sound Quality | Comments                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ------------------------------------- | ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Java Internal Synth with default bank | Low           | Works out of the box. Considering the super small size of the default sound bank, the overall sound balance is quite good actually.                                                                                                                                                                                                                                                                                                    |
| GM SoundFonts                         | Low-Medium    | Difficult to find a well-balanced SoundFont, e.g. you get a nice piano but the bass sucks, etc. No individual effect per instrument. No XG compatibility.                                                                                                                                                                                                                                                                              |
| JJazzLab SoundFont                    | Medium        | Tested on many Yamaha styles. XG compatible, plus a few additional sounds and drum kits. There is an Output Synth configuration preset for a quick setup. No individual effect per instrument.                                                                                                                                                                                                                                         |
| Hardware synthesizer                  | Very good     | In GM mode the mix between individual sounds is usually very good out of the box. Each individual sound can have its own effects (e.g. distortion for guitar, etc.), this has a big impact on the overall rendering. If you find a Cakewalk instrument definition file (.ins) on the web for your synth, you can control it directly from JJazzLab.                                                                                    |
| Software synthesizers                 | Best          | Usually no GM compatibility. Need some effort for the initial set up : virtual Midi device + VST host, select each instrument sound, adjust mix from VST host, ... Each individual sound can have its own effects (e.g. distortion for guitar, etc.), this has a big impact on the overall rendering. Unless you created your own Cakewalk instrument definition file (.ins), you'll need to adjust your setup when you change rhythm. |

Also, when a rhythm does not sound good, you'd be surprised how you can improve things just by trying different instruments and adjusting the mix (volume, effect, panoramic, velocity shift).

If you want to fully customize a backing track, you may simply export to a Midi file, then import the Midi file into your preferred DAW for advanced customization.

For additional information visit the [Midi configuration](configuration/midi-configuration.md) pages.

## I have a Yamaha arranger keyboard (Tyros, PSR, ...), how can I use it with JJazzLab?

JJazzLab can drive your keyboard to benefit from its optimized sounds. Connect your keyboard via Midi and go to the [**Output synth editor**](configuration/output-synth.md#output-synth-editor) and apply the **Yamaha Tyros** preset. This preset is based on Tyros5 which is backwards compatible with previous Tyros models and most of the PSR keyboards.

## How to make fonts bigger? <a href="#font-bigger" id="font-bigger"></a>

In the JJazzLab installation directory, edit the file **etc/jjazzlab.conf** and add **--fontsize 16** (16 or any other value, default is 11) in the **default\_options** variable, you should end up with something like this:

`default_options="--branding jjazzlab -J-Djjazzlab.version=2.2.0 -J-Dplugin.manager.check.new.plugins=true -J-Dplugin.manager.check.interval=EVERY_DAY --fontsize 16"`

Restart JJazzLab. All menus should look bigger now.

This won't solve everything though, as some editor fonts do not depend on this setting. But you can tweak some of them using menu **Tools/Options/Theme**. Check each item in the list and if there is a font defined, change it to make it bigger. The user settings are automatically saved, so you need to do this only once.

## Can I start JJazzLab with command line arguments?

You can pass one or more .sng file names on the command line, JJazzLab will open them upon start.

```
# Example on Win10 (x64)
"C:\Program Files\JJazzLab\bin\jjazzlab64.exe" "C:\my dir\MySong.sng" "D:\AnotherSong.sng"
```

## How to submit a bug? How to find the "log" file?

Send an [email ](https://www.jjazzlab.com/en/contact/)or, if you're a GitHub user, create an [issue](https://github.com/jjazzboss/JJazzLab-X/issues).

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
