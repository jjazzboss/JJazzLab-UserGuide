# 拡張ヤマハスタイル

[YamJJazz](./)[リズムエンジン](./)は、標準[ヤマハスタイル](yamaha-styles.md)ファイル（.sty、.prs、.stなど）の機能を拡張した新しいファイルフォーマット（.yjz）を読み込むことができます。目的は、リズムにより広いダイナミックレンジを持たせ、パターン繰り返しが少ないサウンドになるようデザインすることです。

**拡張スタイル**\(.yjz\)は、以下をサポートします：

* **無制限のバリエーション数** メインA/B/C/Dの代わりに、メインA-1、メインA-2、メインB-1、メインB-2、メインB-3、メインC-1、メインC-2、...とすることができます。 
* **各バリエーション毎に無制限のソースフレーズ数** 標準ヤマハスタイルでは、1つのバリエーションには必ず同じソースフレーズが使われます。  **代替ソースフレーズ**では、リズムデザイナーがメインA-1などのほんの少し異なるフレーズを定義し、YamJJazzエンジンがランダムにそれを使用することで、パターン繰り返しが少ないサウンドを実現します。

{% hint style="warning" %}
.yjzファイルは、**ベーススタイル**である標準ヤマハスタイルファイルの拡張部分に過ぎません。つまり、**MyRhythm.yjz**を読もうとすると、YamJJazzは同じディレクトリに**MyRhythm.sty**（または**MyRhythm.prs**）を見つける必要があります。
{% endhint %}

## 拡張スタイル創作ウィザード

This wizard, available in the **Tools** menu, is used to create a ready-to-be-customized **extended style file** \(.yjz\) from a standard Yamaha style file \(.sty, .prs, ...\). See the  video below for how to use it.

{% hint style="warning" %}
Once created you'll need to manually alter the musical phrases of the .yjz Midi file using a Midi editor or a DAW like Cubase, Ableton Live, etc. Otherwise the new extended style will sound exactly like the base style.
{% endhint %}

## Video tutorial

{% embed url="https://youtu.be/2iVB8t6uAVA" %}

## .yjz file format <a id="yjz-extension-file-format"></a>

{% hint style="info" %}
If you don’t plan to create your own .yjz file you can skip this paragraph.
{% endhint %}

We recommend to use the **Extended style creation wizard** to prepare a .yjz file ready to be customized \(see above\).

The extension file \(.yjz\) must be associated to a base Yamaha style file \(.sty, .prs, .sst, etc.\) with the same name in the same directory.

### Overview <a id="overview"></a>

YamJJazz first reads the **base style** file to get the following Yamaha style information:

* CASM data: channels parameters for each available variation \(used Midi channels, source chords, lower/upper note limits, chord/melody channels, etc.\)
* SINT data: instruments parameters \(bank select/program change, volume, …\)
* Musical data: the Midi source phrases for each channel of each available variation

Then YamJJazz reads the .yjz extension file to get Midi source phrases used to refine the available base variations and to add alternate source phrases.

If the base style uses variation Main A \(example\), then it’s possible to define variations Main A-1, Main A-2, Main A-3, etc. in the extension file. The number is called the complexity level. As soon as you define a Main A-x variation in the extension file, it replaces the original Main A variation from the base file.

If the base file defines variation Main D \(example\) but the extension file does not define Main D-x, then the original Main D will be used with the name Main D-1.

{% hint style="danger" %}
If the base style does not have variation Intro B \(example\), then it’s **not** possible to define Intro B-x in the extension file.
{% endhint %}

### Midi format <a id="midi-format"></a>

**.yjz files use Midi format 1**, they contain several tracks. Note that .sty or .prs files use Midi format 0, they contain a single track.

Each track of the extension file must start with a Midi trackname meta event with the following syntax:

**`trackname=<base variation>-<complexity level>-<id string>-<phrase length in beats>`**

Trackname examples:

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

