# Midi コンフィギュレーション

{% hint style="success" %}
Midiでわずらわしいことをしたくない場合は、[JJazzLab サウンドフォント](jjazzlab-soundfont/)を使ってください。
{% endhint %}

## 概要

![](../.gitbook/assets/midiwizard-image1%20%282%29.png)

JJazzLabはMidiアプリケーションです。JJazzLabはオーディオ出力を直接生成するのではなく、Midiメッセージ（例：「ベースでDを弾いて」）を生成し、 **Midi**  **出力デバイス** 通して [**シンセ出力**](output-synth.md)に送信します。 

**Midi出力デバイス**は、メニューの **Tools/Options/Midi**で選択できます。

**Midi出力デバイス** は、MidiまたはUSBケーブルで外部のハードウェアシンセに接続するか、ソフトウェアシンセ（VSTインストゥルメント、サウンドフォントプレーヤーなど）の**仮想Midiポート**を通して接続する必要があります。ウェブ上には、Windowsの[LoopBe1 ](https://nerds.de/en/loopbe1.html)Linuxの [Virmidi ](https://alsa.opensrc.org/Virmidi)のような無料の仮想MIDIポートがあります。

{% hint style="warning" %}
Windowsで**VirtualMidiSynth**サウンドフォントプレーヤーを使用する場合は、**仮想Midiポート** は必要ありません。このアプリケーションは、 **Midi出力デバイス**として自身をインストールするからです。
{% endhint %}

**シンセ出力** は音を出します。もしJJazzLabが**シンセ出力**の機能を知れば、JJazzLabは [**ミックスコンソール**](../songs/song-editors/mix-console.md)から直接それをコントロールすることができます。そして最も重要なことは、リズムを選択するとJJazzLabは自動的に関連するサウンドを選択し、必要に応じてドラムマップ変換を行うことです。

## Midiコンフィギュレーションウイザード <a id="midi-configuration-wizard"></a>

このウィザードは、最適なMIDIコンフィギュレーションを選択するのに便利です。 このウィザードは、JJazzLab を初めて起動したときに自動的に起動します。メニューの**Tools/Midi Configuration Wizard**から手動で起動することもできます。

