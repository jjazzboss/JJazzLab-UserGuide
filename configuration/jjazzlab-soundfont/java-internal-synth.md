# Java internal synth

The Java runtime engine used by JJazzLab has an internal Midi synth (sometimes callled Gervill).

If you don't load a SoundFont file it will use its built-in GM sounds.

{% hint style="warning" %}
The built-in GM sounds are not good quality sounds, but it can be enough to test JJazzLab. The good thing is that no setup is required, it will work out-of-the-box.
{% endhint %}

## Initial setup with the JJazzLab SoundFont <a href="setup-instructions" id="setup-instructions"></a>

{% hint style="warning" %}
The Java internal synth is not high-performance. When used with a large SoundFont like the JJazzLab SoundFont you may hear some dropped notes when too many notes are played.&#x20;
{% endhint %}

1. Download **JJazzLab-SoundFont.sf2** from the [Musical Artefacts web site](https://musical-artifacts.com/artifacts/1036) \

2. In the JJazzLab **Midi options**, select the **Java Internal Synth** and load the **JJazzLab-SoundFont.sf2**\
   ****\
   ****![](../../.gitbook/assets/LoadSoundFont-JavaSynth.png)   \

3. Go to the **Output Synth Editor** and apply the preset **Java Internal Synth**\
   ****\
   ****![](../../.gitbook/assets/OutputSynth-PresetJavaSynth.png)

{% hint style="info" %}
If you’re on Mac OSX the [Midi configuration wizard](../midi-configuration.md#midi-configuration-wizard) will automatically perform the same steps if you choose to use the JJazzLab SoundFont.
{% endhint %}
