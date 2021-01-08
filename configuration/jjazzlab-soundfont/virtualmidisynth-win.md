# VirtualMIDISynth \(win\)

**VirtualMIDISynth** is a free, lightweight and efficient SoundFont player for Windows. 

It is implemented as a Windows multimedia user driver, so it is directly accessible as a standard MIDI out device -no need for a virtual Midi port.

{% hint style="success" %}
VirtualMIDISynth can also convert Midi files to .mp3. This way you can easily get a JJazzLab backing track as an audio file. See the [FAQ](../../faq.md#generate-mp3) for more info.
{% endhint %}

## Initial setup

1. Download **JJazzLab-SoundFont.sf2** from the [Musical Artefacts web site](https://musical-artifacts.com/artifacts/1036)  
2. Download and install **VirtualMIDISynth** from the [CoolSoft web site](https://coolsoft.altervista.org/virtualmidisynth) Accept all installer default settings. 
3. Load the Soundfont in **VirtualMIDISynth** ![](../../.gitbook/assets/vms-loadsoundfont.png)  ****Click on the pen icon if you need to adjust the default volume \(0-500%\) of the SoundFont.  
4. Start JJazzLab and go to **Options/Midi**, set **VirtualMIDISynth** as the **Midi OUT device**      ![](../../.gitbook/assets/vms-setmididevice.png)  
5. Go to the [output synth](../output-synth.md) editor and apply the preset **VirtualMIDISynth** ![](../../.gitbook/assets/outputsynth-presetvms.png) ****

{% hint style="info" %}
On Windows the [Midi configuration wizard](../midi-configuration.md#midi-configuration-wizard) will automatically perform steps 4 \(if VirtualMIDISynth is installed\) and 5 if you choose to use the JJazzLab SoundFont.
{% endhint %}

