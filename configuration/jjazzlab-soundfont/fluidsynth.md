# FluidSynth \(Linux/Mac\)

[FluidSynth](https://www.fluidsynth.org/)は、多くのプラットフォームに対応した、無料で効率的なサウンドフォントプレーヤーです。LinuxとMacOS用に推奨します。

{% hint style="success" %}
FluidSynth は、リダイレクトして .wav ファイルとして出力することができます。これによりJJazzLabバッキングトラックをオーディオファイルとして取得するのに使うことができます。詳しい情報は、[FAQ](../../faq.md#generate-mp3)を参照してください。
{% endhint %}

## 初期設定

1. **JJazzLab-SoundFont.sf2**を[Musical Artefacts ウェブサイト](https://musical-artifacts.com/artifacts/1036)からダウンロードします。 
2. Install a virtual midi port

   ```text
   $ sudo modprobe snd-virmidi midi_devs=1
   ```

   ⚠ Previous command will work for the current session only. If you want to permanently add the virtual midi device \(jack users on Debian/Ubuntu/Mint\), edit the **/etc/modules** file to add **snd-virmidi**, and create a file /etc/modprobe.d/snd-virmidi\_options.conf with the content `options snd-virmidi midi_devs=1`.  


   If you list the connected ports, you should see a new **Virtual Raw Midi** entry like below:

   ```text
   $ aconnect -lo  
   client 14: 'Midi Through' [type=kernel]  
       0 'Midi Through Port-0'  
   client 20: 'Virtual Raw MIDI 1-0' [type=kernel,card=1]  
       0 'VirMIDI 1-0'
   ```

3. Install **FluidSynth** and **QSynth**, its graphical user interface  
   \(tested OK on Linux Mint, if problem please consult the FluidSynth documentation\)

   ```text
   $ sudo apt-get update -y            # Get latest packages info
   $ sudo apt-get install fluidsynth
   $ sudo apt-get install qsynth
   ```

4. Start **QSynth**

   ```text
   qsynth &
   ```

   ![](../../.gitbook/assets/fluidsynth-qsynth.png)   

5. Load the **JJazzLab SoundFont** and adjust **FluidSynth** settings  ![](../../.gitbook/assets/qsynth-loadsoundfont.png)  ![](../../.gitbook/assets/qsynth-midisettings.png)   ![](../../.gitbook/assets/qsynth-audiosettings.png) 
6. Connect the virtual port to **FluidSynth**  
  
   You should see a new port, like in the example below:

   ```text
   $ aconnect -lo
   client 14: 'Midi Through' [type=kernel]
       0 'Midi Through Port-0'
   client 20: 'Virtual Raw MIDI 1-0' [type=kernel,card=1]
       0 'VirMIDI 1-0     '
   client 128: 'FLUID Synth (Qsynth1)' [type=user,pid=3099]
       0 'Synth input port (Qsynth1:0)'
   ```

   Connect the Virtual Port to the entry of the **FluidSynth**:

   ```text
   $ aconnect 20:0 128:0      # Values might be different on your system
   ```

   ⚠ This connection needs to be restored each time the **FluidSynth** engine is restarted.  

7. In JJazzLab go to **Options/Midi** and select the first **virMIDI** out device  ![](../../.gitbook/assets/fluidsynth-setmididevice.png) 
8. [シンセ出力](../output-synth.md)エディターに進み\[訳注：鍵盤アイコンをクリック\]、プリセットの **FluidSynth**を適用します。  ****![](../../.gitbook/assets/outputsynth-presetfluidsynth.png)

{% hint style="info" %}
The start of FluidSynth with the virtual Midi port can be automated via a shell script.

On Linux the [Midi configuration wizard](../midi-configuration.md#midi-configuration-wizard) will automatically perform step 8 if you choose to use the JJazzLab SoundFont.
{% endhint %}

