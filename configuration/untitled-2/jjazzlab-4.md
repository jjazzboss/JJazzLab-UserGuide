# Java internal synth

The Java engine used by JJazzLab has an integrated synth \(called Gervill\) which can load SoundFonts. Unfortunately this Java Internal Synth is not high-performance and you may hear some dropped notes when too many notes are played. So when possible prefer an external SoundFont player, such as VirtualMIDISynth on Windows or FluidSynth on Linux.

## Setup instructions <a id="setup-instructions"></a>

1. Download JJazzLab-SoundFont.sf2 from the [Musical Artefacts web site](https://musical-artifacts.com/artifacts/1036)
2. In the Midi options/preferences, select the Java Internal Synth and load JJazzLab-SoundFont.sf2 
3. Go to the Output Synth Editor and apply the preset ‘Java Internal Synth’ 

This setup has to be done _only once_, the settings are restored automatically when you restart JJazzLab.

If you’re on Mac OSX the Midi Configuration Wizard will automatically perform the same steps if you choose to use the JJazzLab SoundFont.

