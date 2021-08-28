# シンセ出力



{% hint style="info" %}
JJazzLab サウンドフォントをお使いの方は、このページを飛ばして [JJazzLab サウンドフォント](jjazzlab-soundfont/) のページに直接に進んでください。 
{% endhint %}

## シンセ出力の概念 <a id="output-synth-concept"></a>

シンセ出力とは、JJazzLabの出力に接続されているMIDIシンセを表しています：

![](../.gitbook/assets/outputsynth-concept%20%281%29.png)

シンセ出力の情報によって、JJazzLabはシンセを直接コントロールすることが可能となります。[ミックスコンソール](../songs/song-editors/mix-console.md)から直接楽器を選択したり、曲をロードしたときにソングミックスを自動的に復元したりできるのはこのためです。

シンセ出力の情報は、JJazzLabでも2つの重要な作業に使われています：

1. 自動的に新しいリズムに最適な楽器を選択
2. 自動的に必要に応じてドラムサウンドをリマップする（例：[XGドラムマップ](https://www.jjazzlab.com/images/doc/XG-DrumMap.png)から[GMドラムマップ](https://en.wikipedia.org/wiki/File:GMStandardDrumMap.gif)に変更）

{% hint style="danger" %}
JJazzLabでのシンセ出力のコンフィギュレーションが実際のシンセ出力と一致していない場合（例えば、GM以外のVSTインストゥルメントを使用しているのに、JJazzLabではGMに対応していると思い込んでいる場合）、楽器の選択に問題が生じ、バッキングトラックがかなり変な音になってしまうことがあります。
{% endhint %}

## シンセ出力エディター

**シンセ出力**機能は**シンセ出力エディター**で編集できます。 

![](../.gitbook/assets/outputsyntheditor.png)

シンセ出力の設定は、ファイルの読み込み／ファイルに保存ができます。デフォルトでは、JJazzLabは **Default.cfg**を使用します。

## 例

GM互換の古いローランドのシンセサイザーをJJazzLabに接続しました。そのため、**シンセ出力エディター**で**GM compatible**にチェックを入れています。

曲でSimpleFolk.styというリズムを使っています。これはヤマハスタイルで、3つの楽器を定義しています：

* ベース、適切な楽器は、GM ‘Acoustic Bass’です。
* ギター、適切な楽器は、XG ‘12 String Guitar’です。
* ドラム、適切なドラムキットは、XG drumsのキーマップを使用した「Brush」タイプのドラムキットです。

シンセ出力の情報（「このシンセはGMにしか対応していない」）を使って、JJazzLabは曲を演奏する前に次のようなことを行います：

* ローランドのシンセに、**GMモードONに切り替え** というMIDIメッセージを送信
* ベース：標準GMメッセージを通してGM ‘Acoustic Bass’を選択
* ギター：XG ‘12 String Guitar’に最も近い楽器であるGM ‘Steel Guitar’を選択
* ドラム：GM standard drumsを選択（GMはドラムキットを1つしか持っていない）し、XG固有のドラム音をすべてGMのドラム音にリマップ

{% hint style="success" %}
結論として、JJazzLabはシンセ出力の情報を使って、（リズムデザイナーがプログラムした）オリジナルのリズムに近い音を出すことができます。
{% endhint %}

## 一般的な設定

### プリセット

シンセ出力が以下の構成のいずれかに該当する場合、シンセ出力エディターのメニューバーから対応するプリセットを適用するだけでかまいません。

* **GM**: GM互換シンセ
* **JJazzLab SoundFont**: JazzLabサウンドフォントをロードしたサウンドフォントプレイヤー
* **Yamaha Tyros**: TyrosまたはPSRシリーズのヤマハアレンジャーキーボード

### GM2/GS/XG 互換シンセ

設定を**リセット**し、該当するチェックボックスを選択してください。この3つの規格はGMを包括しているので、GMのチェックを外すことができます。

ヤマハスタイルではXGがベスト、GM2やGSはGMより良いでしょう。

シンセの中には、規格に互換性があり、さらに追加のサウンドを持つものが多くあります。この場合は、互換性のチェックボックスを選択し、以下の「その他のシンセ」と同様の操作を行います。

### その他のシンセ（VST、ハードウェアシンセ、他）

シンセに1つまたは複数の[MIDIシンセ定義ファイル](output-synth.md#midi-synth-definition-files-cakewalk-ins-format) を追加する必要があります。

### Controlling the mix outside of JJazzLab

You may want to prevent JJazzLab from controlling your synth via Midi, because you control it directly \(e.g. you set instruments, volumes, etc. directly on the synth\).

To achieve this you need to disable the **Midi parameters** in the **mix console**, so that JJazzLab only send Midi notes but no program/controller change Midi messages.

You can do it globally for all channels via the **Midi menu**: 

![](../.gitbook/assets/2021-01-06-22_02_58-jjazzlab.png)

Or do it channel by channel, and parameter by parameter, via the **channel settings**:

![](../.gitbook/assets/channelsettings.png)

Note that once all Midi parameters are disabled, output synth configuration becomes useless since JJazzLab will not send any Midi message to change the instruments \(Bank Select/Program Midi messages\).

## Midi synth definition files \(.ins\) <a id="midi-synth-definition-files-cakewalk-ins-format"></a>

JJazzLab can read Cakewalk instrument definition files \(.ins\). An instrument definition file defines a **Midi synth** with its list of instruments and how to select them via Midi \(Bank Select/Program Change values\).

JJazzLab ships with .ins files for a few existing hardware synthesizers \(e.g. Yamaha Motif, Korg X-50, …\). If you don’t find an .ins file for your sound device, you can search the web or create your own \(google “Cakewalk Instrument Definition File” for help\).

Use the **Add** \(Synths\) button to add one or more .ins files to the current output synth configuration: 

![](../.gitbook/assets/outputsynth-addsynth.png)

{% hint style="info" %}
Once a **Midi synth** has been added, its instruments become available in the instrument selection dialog in the **mix console**.
{% endhint %}

See the [JJazzLab .ins format extensions](output-synth.md#jjazzlab-ins-format-extensions) paragraph below if you want your .ins to be optimized for JJazzLab.

## Default instruments <a id="default-instruments"></a>

The **output synth editor** lets you map standard GM Instruments to **default instruments** of your choice. You can also set a **default instrument** for an instrument **family**, e.g. all the organs.

![If a rhythm needs GM Bright Piano, then Hard FM EP will be used instead](../.gitbook/assets/outputsynth-defaultinstruments.png)

## JJazzLab .ins format extensions <a id="jjazzlab-ins-format-extensions"></a>

{% hint style="info" %}
These .ins format extensions are not mandatory to use for JJazzLab to work. But they are required if you have a custom .ins file and want to fully benefit from the JJazzLab features in order to get better sounding backing tracks.
{% endhint %}

The standard .ins file format lacks some information for JJazzLab to fully optimize instrument selection and **drum map** conversion.

For an optimum use JJazzLab needs:

1. For melodic instruments: its **GM substitute** instrument  Example: the **GM substitute** for the XG instrument ‘12 String Guitar’ is the GM instrument ‘Steel Guitar’
2. For percussion instruments/drum kits: its **type** and its **drum key map**

Therefore some \(optional\) extensions have been introduced, as show in the examples below.

```text
;
; {{ SubGM1= }}
;
[PRE1]
0=Pn:Full Concert Grand {{ SubGM1=0 }}       ; substitute = GM Acoustic Piano
1=Pn:Rock Grand Piano   {{ SubGM1=1 }}       ; substitute = GM Bright Piano 
2=Pn:Mellow Grand Piano {{ SubGM1=0 }}       ; substitute = GM Acoustic Piano
5=Pn:Aggressive Grand   {{ SubGM1=1 }}       ; substitute = GM Bright Piano
...
18=Pn:CP 1979           {{ SubGM1=3 }}       ; substitute = GM Electric Grand Piano
19=Pn:CP70 Chorus       {{ SubGM1=3 }}       ; substitute = GM Piano
...
```

```text
;
; {{ DrumKit=,  }}
;          : STANDARD, POWER, ROOM, ELECTRONIC, ANALOG, JAZZ, BRUSH, ORCHESTRA, SFX
;  : GM, GS_GM2, XG
;
[DR:PRE]
0=Dr:Power Standard Kit 1   {{DrumKit=POWER, XG}} 
1=Dr:Power Standard Kit 2   {{DrumKit=POWER, XG}} 
2=Dr:Hyper Standard Kit     {{DrumKit=STANDARD, XG}} 
3=Dr:Dry Standard Kit       {{DrumKit=ROOM, XG}} 
...
```

```text
;
; {{ UseGsInstruments }}       => For melodic instrument selection a GS Sysex message will be sent to make sure channel is in melodic mode
; {{ UseGsDrumsInstruments }}  => For drums instrument selection a GS Sysex message will be sent to make sure channel is in percussion mode
;
[JJazzLab SoundFont (GS)]
BankSelMethod=1                                ; Use Bank Select MSB only
Patch[0]=GM Bank  {{ UseGsInstruments }}       ; This bank stores GS melodic instruments
Patch[128]=Bank 1 {{ UseGsInstruments }}       ; This bank stores GS melodic instruments 
Patch[256]=Bank 2 {{ UseGsInstruments }}       ; This bank stores GS melodic instruments
...
Patch[*]=Drums    {{ UseGsDrumsInstruments }}  ; This bank stores GS drums instruments
...
```

