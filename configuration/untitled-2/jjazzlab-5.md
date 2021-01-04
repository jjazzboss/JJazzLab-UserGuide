# JJazzLab

JJazzLab is a Midi-based application. It does _not_ directly generate audio output, rather it generates Midi messages \(eg “play a D on the bass”\) which are sent to a sound device via a Midi connection. That’s why JJazzLab needs to know about your Midi configuration in order to work properly.

In general we recommend to [use the JJazzLab SoundFont](https://www.jjazzlab.com/en/doc/jjazzlab-soundfont).

If you’re familiar with Midi and use a hardware synthesizer or VST/AU instruments, then learn about the [Output Synth Editor](https://www.jjazzlab.com/en/doc/output-synth-editor).

## Midi Configuration Wizard <a id="midi-configuration-wizard"></a>

This wizard will help you select the best Midi configuration.

It is launched automatically the first time you run JJazzLab. You can also run it manually from the _menu Tools/Midi Configuration Wizard_.

## Drums issues with GM-only compatible sound devices <a id="GM-drums-issue"></a>

A GM-only compatible sound device normally accepts drums/percussion data _only_ on channel 10. What if the JJazzLab song needs more than one drums channel ?

This typically happens for rhythms which have a drum track on channel 10 and another percussion track \(say channel 9\). This also happens if a song uses 2 different rhythms. Note that this should never happen if you [use the JJazzLab SoundFont](https://www.jjazzlab.com/en/doc/jjazzlab-soundfont).

The consequence is that when you play the song you hear strange repetitive sounds. For example because JJazzLab sends percussion data on channel 9 while the sound engine has a piano sound on channel 9.

So what can be done ?

* If your synth can handle several drum channels, use the [Output Synth Editor](https://www.jjazzlab.com/en/doc/output-synth-editor) to tell JJazzLab how to use this capability
* Enable the Drums rerouting option  JJazzLab can reroute non channel-10 drums/percussion tracks to channel 10. JJazzLab will automatically propose to activate this option upon playback if it detects a potential problem. The option can also be manually activated in the settings dialog of each drums-type channel in the Mix Console \(see image below\).  

