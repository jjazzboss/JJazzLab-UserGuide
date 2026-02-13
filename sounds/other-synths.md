---
JJazzLabを他のシンセサイザーにMIDIを通して接続する方法
---

# 他のシンセサイザー

一般的には、[FluidSynth](using-fluidsynth.md)の使用をお勧めします：セットアップ不要で適切なサウンドです。&#x20;

ただし、高品質なハードウェアまたはソフトウェアシンセ（VST、AU、AAXなど）をお持ちの場合は、MIDIケーブルまたは仮想MIDIケーブル/デバイス（Windows用のLoopMIDIなど）を介してJJazzLabで使用できます。

![Connecting a Midi synth to JJazzLab](<../.gitbook/assets/MidiWizard-image1 (1).png>)

**ツール/設定**タブの**Midi**タブにおいて

* 「use FluidSynth」の選択を外す
* Midi OUT deviceを選択する
* 接続したシンセサイザーの機能が書いてあるOutput Synthを選択してください。&#x20;

The **Output Synth**情報は、JJazzLabがミックスコンソールから直接シンセサウンド/楽器を表示・選択できるようにします。この情報は必要に応じてドラムサウンドの再マッピングにも使用されます（ヤマハスタイルはXGドラムマップを使用しますが、お使いのシンセは異なる場合があります）。 

{% hint style="danger" %}
間違った楽器の音（例：ベース音の代わりにピアノ音など）が聞こえる場合、または[ミックスコンソール](../editors/mix-console.md)から楽器を選択できない場合は、通常、接続したシンセサイザーと**Output Synth**の情報が一致していないことを意味します。例えば、非GMシンセを接続しているのに、**Output Synth**がGMシンセに設定されている場合などが該当します。{% endhint %}

出力シンセの事前定義済みリストは下記の通りです。お使いのシンセに追加機能がある場合、「**Add a synth from file...**」を使用して、MIDIシンセ定義ファイル（.ins）を読み込むことができます。.insファイル形式の詳細については、以下を参照してください。
<figure><img src="../.gitbook/assets/2023-12-31 18_23_58-Options.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
ソフトウェアシンセ（例：VSTプラグイン）を使用する場合、サウンド選択やミックス設定（音量、エフェクトなど）をVSTプラグインのインターフェースから直接制御したい場合があります。この場合、JJazzLabがMIDIノートのみ送信するように、JJazzLabのミックスコンソールから[Disable all Midi parameters(すべてのMIDIパラメーターを無効化)](../editors/mix-console.md#menu-midi)する必要があります。
{% endhint %}

## Midi synth definition files (.ins)

JJazzLabは、**Cakewalk instrument definition files** (.ins)が読み込むことができます。これらのファイルは多くのDAWで使用されています。.ins形式に関する詳細情報はウェブで検索してください。

**.ins**ファイルは、楽器のリストとMIDI経由での選択方法（バンクセレクト/プログラムチェンジ値）を定義する**Midi synth**を記述します。

### JJazzLab .ins 拡張子 <a href="#jjazzlab-ins-format-extensions" id="jjazzlab-ins-format-extensions"></a>

{% hint style="info" %}
これらの.ins形式の拡張子は、JJazzLabを動作させるために必須ではありません。ただし、カスタムの.insファイルを使用し、より良い音質のバッキングトラックを得るためにJJazzLabの機能を最大限に活用したい場合には必要です。
{% endhint %}

標準の.insファイル形式では、JJazzLabが楽器選択と**drum map**変換を完全に最適化するための必要な情報が不足しています。

最適にJJazzLabを使用するには必要なもの:

1. メロディ楽器用: その**GM substitute(代替)**楽器\
   &#x20;例：XG楽器「12 String Guitar」の**GM substitute**は、GM楽器「Steel Guitar」です。
2. 打楽器／ドラムキット用: その**type**および、その**drum key map**

そうすると、以下の例に示すように、「\{{ xxxx \}}」という（オプションの）キーワード拡張が導入されます。

```
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

```
;
; {{ DrumKit= type, keymap }}
;   type=STANDARD, POWER, ROOM, ELECTRONIC, ANALOG, JAZZ, BRUSH, ORCHESTRA, SFX
;   keymap=GM, GS_GM2, XG
;
[DR:PRE]
0=Dr:Power Standard Kit 1   {{DrumKit=POWER, XG}} 
1=Dr:Power Standard Kit 2   {{DrumKit=POWER, XG}} 
2=Dr:Hyper Standard Kit     {{DrumKit=STANDARD, XG}} 
3=Dr:Dry Standard Kit       {{DrumKit=ROOM, XG}} 
...
```

シンセがGS互換の場合、2つの特別なキーワード拡張機能も利用できます:

```
; For GS-compatible synths only
; {{ UseGsInstruments }}       => メロディ楽器の選択時には、チャンネルがメロディモードであることを確認するためGS Sysexメッセージが送信されます
; {{ UseGsDrumsInstruments }}  => ドラム楽器の選択時には、チャンネルがパーカッションモードであることを確認するためGS Sysexメッセージが送信されます
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
