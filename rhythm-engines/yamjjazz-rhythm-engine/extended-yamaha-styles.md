# 拡張ヤマハスタイル

[YamJJazz](./)[リズムエンジン](./)は、標準[ヤマハスタイル](yamaha-styles.md)ファイル（.sty、.prs、.stなど）の機能を拡張した新しいファイルフォーマット（.yjz）を読み込むことができます。目的は、リズムにより広いダイナミックレンジを持たせ、パターン繰り返しが少ないサウンドになるようデザインすることです。

**拡張スタイル**\(.yjz\)は、以下をサポートします：

* **無制限のバリエーション数** メインA/B/C/Dの代わりに、メインA-1、メインA-2、メインB-1、メインB-2、メインB-3、メインC-1、メインC-2、...とすることができます。 
* **各バリエーション毎に無制限のソースフレーズ数** 標準ヤマハスタイルでは、1つのバリエーションには必ず同じソースフレーズが使われます。  **代替ソースフレーズ**では、リズムデザイナーがメインA-1などのほんの少し異なるフレーズを定義し、YamJJazzエンジンがランダムにそれを使用することで、パターン繰り返しが少ないサウンドを実現します。

{% hint style="warning" %}
.yjzファイルは、**ベーススタイル**である標準ヤマハスタイルファイルの拡張部分に過ぎません。つまり、**MyRhythm.yjz**を読もうとすると、YamJJazzは同じディレクトリに**MyRhythm.sty**（または**MyRhythm.prs**）を見つける必要があります。
{% endhint %}

## 拡張スタイル作成ウィザード

**ツール（Tools）** メニューにあるこのウィザードは、標準のヤマハスタイルファイル\(.sty, .prs, ...\)から、すぐにカスタマイズできる**拡張スタイルファイル**\(.yjz\) を作成するためのものです。操作方法は以下のビデオをご覧ください。

{% hint style="warning" %}
作成後は、MIDIエディターやCubase、Ableton LiveなどのDAWを使って、.yjz MIDIファイルの音楽フレーズを手動で変更する必要があります。そうしないと、新しいエクステンデッド・スタイルはベーススタイルと全く同じ音になってしまいます。
{% endhint %}

## ビデオチュートリアル

{% embed url="https://youtu.be/2iVB8t6uAVA" %}

## .yjzファイルフォーマット <a id="yjz-extension-file-format"></a>

{% hint style="info" %}
独自の.yjzファイルを作成する予定がない場合は、この項目を読み飛ばしても構いません。
{% endhint %}

**拡張スタイル作成ウィザード**を使用して、カスタマイズ可能な.yjzファイルを準備することをお勧めします（上記参照）。

拡張ファイル（.yjz）は、同じディレクトリにある同名のベースとなるヤマハスタイルファイル（.sty、.prs、.stsなど）に関連付けられている必要があります。

### 概要 <a id="overview"></a>

YamJJazzは、最初に**ベーススタイル**ファイルを読み込んで、次のようなヤマハスタイル情報を得ます：

* CASM データ：バリエーションごとのチャンネルパラメーター（使用するMIDIチャンネル、ソースコード、ノートの下限／上限、コード／メロディーのチャンネルなど
* SINT データ：楽器パラメーター（バンク選択／プログラムチェンジ、音量など）
* Musical データ：使用する各バリエーションの各チャンネルのMIDIソースフレーズ

その後、YamJJazzは.yjz拡張ファイルを読み込んで、ベースとなる使用するバリエーションを改良したり、代替ソースフレーズを追加したりするためのMIDIソースフレーズを取得します。

ベーススタイルがバリエーションのメインA（例）であれば、拡張ファイルでバリエーションのメインA-1、メインA-2、メインA-3などを定義することが可能です。その数を「複雑度」と呼びます。拡張ファイルでMain A-xのバリエーションを定義するとすぐに、ベースファイルの元のMain Aのバリエーションを置き換えます。

ベースファイルにバリエーションメインD（例）が定義されていても、エクステンションファイルにメインD-xが定義されていない場合、オリジナルのメインDがメインD-1という名前で使用されます。

{% hint style="danger" %}
ベーススタイルにバリエーションIntro Bが定義されていない場合（例）、拡張ファイルにIntro B-xを定義することはできません。
{% endhint %}

### MIDIフォーマット <a id="midi-format"></a>

**.yjzファイルはMIDIフォーマット1を使用しており**、 複数のトラックを含んでいます。なお、.styまたは.prsファイルはMidiフォーマット0を使用しており、1つのトラックを含んでいます。

拡張ファイルの各トラックは、次のような構文のMIDIトラック名メタイベントで始まる必要があります。

**`trackname=<base variation>-<complexity level>-<id string>-<phrase length in beats>`**

トラック名の例：

* Main A-1-drums-8
* Main A-1-bass-8
* Main A-1-guitar-8
* Main A-1-guitar\_root-8
* Main A-2-drums-8
* Main A-2-bass-8
* Main A-2-guitar-8
* Main A-2-guitar\_root-8
* Ending B-1-piano-4
* Ending B-1-bass-4

For `<id string>` you can use whatever string you like, but it's a good practice to mention at least the target instrument. If you use the **Extended style creation wizard**, `id string` is generated for you and will be something like `[Bass, C7M, ch11]` : the instrument name, the **source chord** and **source Midi channel**.

All tracks for a given variation must have the same length in beats. But different variations can have different lengths.

{% hint style="warning" %}
Depending on the CASM data, there might be more than one source phrase for a given instrument \(the guitar and guitar\_root phrases in the example above\). For example one channel can be used for major chords, the other one for minor chords.
{% endhint %}

A track should only contain Midi note on/off messages for its **source chord** and **source Midi channel,** as defined in the CASM data of the base style. If you used the **Extended style creation wizard**, you have the **source chord** and **Midi channel** indicated in the `<id string>`, as explained above.

### Alternate source phrases <a id="alternate-takes"></a>

To add **alternate source phrases** for a given variation, just append source phrases on each track of this variation. Each appended source phrase must have the same length than the original phrase.

**Example**  
The source phrase length of track Main A-1-bass-8 is 8 beats \(2 bars in 4/4\). You can append 2 similar 8-beat source phrases on that track, so the track length becomes 24 beats. YamJJazz will consider the 2 appended phrases as **alternate source phrases** of the first source phrase, to be used randomly when rendering the Main A-1 bass part. 

Note that 2 alternate source phrases must be also added for all the other Main A-1 tracks: Main A-1-drums-8, Main A-1-guitar-8 and Main A-1-guitar\_root-8.

{% hint style="info" %}
If you have for example 3 source phrases for Main A-1, JJazzLab will randomly pick a source phrase every 2 bars. The selection is actually not 100% random: the first source phrase has more chances to be selected than the second one, and the second one has more chances to be selected than the third one, etc. In other words the last source phrase has the least chances to get selected.
{% endhint %}

