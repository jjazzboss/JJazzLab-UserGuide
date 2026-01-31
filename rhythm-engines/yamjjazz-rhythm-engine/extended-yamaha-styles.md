# 拡張ヤマハスタイル

[YamJJazzリズムエンジン](./)は、標準的な[ヤマハスタイル](yamaha-styles.md)ファイル（.sty、.prs、.sstなど）の機能を拡張する新しいファイル形式（.yjz）を読み取ることができます。目的は、より広いダイナミックレンジを持ち、繰り返しが少なく聞こえるリズムの設計を可能にすることです。

.yjzファイルは、以下の例に示すように、既存のヤマハスタイルの音楽を簡単に変更するためにも使用できます。

**extended style**（.yjz）は以下をサポートします :

* **無制限のバリエーション**\
  MainA/B/C/Dの代わりに、MainA-1、MainA-2、MainB-1、MainB-2、MainB-3、MainC-1、MainC-2、…と設定できます。<br>
* **各バリエーションにつきソースフレーズの数が無制限**\
  標準のヤマハスタイルでは、特定のバリエーションに対して常に同じソースフレーズが使用されます。**代替ソースフレーズ**機能により、リズムデザイナーは例えばMainA-1用に異なるが類似したフレーズを定義でき、YamJJazzエンジンがランダムに使用することで反復感を軽減します。

{% hint style="warning" %}
.yjzファイルは、標準的なヤマハスタイルファイル（**基本スタイル**）の拡張部分に過ぎません。したがって、**MyRhythm.yjz**を読み込む際、YamJJazzは同じディレクトリ内に**MyRhythm.sty**（または**MyRhythm.prs）**がある必要があります。
{% endhint %}

## 拡張スタイル作成ウィザード

このウィザードは、**ツール**メニューから利用でき、標準のヤマハスタイルファイル（.sty、.prsなど）からカスタマイズ可能な**extended style file**（.yjz）を作成するために使用します。使用方法については、以下の動画をご覧ください。

{% hint style="warning" %}
作成後は、MIDIエディターやCubase、Ableton LiveなどのDAWを使用して、.yjz MIDIファイルの音楽フレーズを手動で変更する必要があります。そうしないと、新しい拡張スタイルはベーススタイルと全く同じ音になります。
{% endhint %}

### 簡単な例：既存のヤマハスタイルのMain Aを変更

例えば、ヤマハスタイルの**MediumJazzS737.sst**の**Main A**バリエーションの音楽を変更したいとしましょう。

**拡張スタイル作成ウィザード(Extended style creation wizard)**を起動し、リズム**MediumJazzS737.sst**を選択した後、下図のように設定を調整してください。

<figure><img src="../../.gitbook/assets/2023-01-03 16_45_42-Extended style creation wizard.png" alt=""><figcaption><p>代替ソースフレーズなしで、Main Aセクションのみを変更するウィザード設定</p></figcaption></figure>

**MediumJazzS737-ext.yjz**が生成されたら、MIDIエディタで開いてください。例えばCubaseを使用している場合、以下のような表示になるはずです：

<figure><img src="../../.gitbook/assets/2023-01-03 16_59_55-Cubase AI 7 - [Cubase AI 7 Project - Untitled1].png" alt=""><figcaption></figcaption></figure>

トラック名に指定されたコード（例：ベーストラックのC7M）に基づき、MIDIソースフレーズを自由に編集できます。_トラック名やセクションの長さ（ここでは8小節/32拍）を変更してはなりません_。

{% hint style="info" %}
1つの楽器に対して複数のソースフレーズが表示される場合があります。この例ではベースに2つのトラックがあります。それぞれのトラックに対して一貫した変更を加える必要があります。&#x20;

The reason why this happens in Yamaha styles is beyond the scope of this tutorial. The general idea is to allow specialized phrases for specific cases, e.g. a phrase for minor chords and another one for major chords. Search for the Yamaha style CASM section if you want more information about this.
{% endhint %}

When the Midi editing is complete, save your file.&#x20;

In JJazzLab start a **Rescan** in Options/Rhythms.

Now you can use the new modified style in your song, just select **MediumJazzS737-ext.yjz** from the **YamJJazz extended styles** as seen below.&#x20;

<figure><img src="../../.gitbook/assets/2023-01-03 17_49_15-JJazzLab  3.2.1.png" alt=""><figcaption></figcaption></figure>

## Video tutorial

{% embed url="https://youtu.be/2iVB8t6uAVA" %}

## .yjz file format <a href="#yjz-extension-file-format" id="yjz-extension-file-format"></a>

{% hint style="info" %}
If you don’t plan to create your own .yjz file you can skip this paragraph.
{% endhint %}

We recommend to use the **Extended style creation wizard** to prepare a .yjz file ready to be customized (see above).

The extension file (.yjz) must be associated to a base Yamaha style file (.sty, .prs, .sst, etc.) with the same name in the same directory.

### Overview <a href="#overview" id="overview"></a>

YamJJazz first reads the **base style** file to get the following Yamaha style information:

* CASM data: channels parameters for each available variation (used Midi channels, source chords, lower/upper note limits, chord/melody channels, etc.)
* SINT data: instruments parameters (bank select/program change, volume, …)
* Musical data: the Midi source phrases for each channel of each available variation

Then YamJJazz reads the .yjz extension file to get Midi source phrases used to refine the available base variations and to add alternate source phrases.

If the base style uses variation Main A (example), then it’s possible to define variations Main A-1, Main A-2, Main A-3, etc. in the extension file. The number is called the complexity level. As soon as you define a Main A-x variation in the extension file, it replaces the original Main A variation from the base file.

If the base file defines variation Main D (example) but the extension file does not define Main D-x, then the original Main D will be used with the name Main D-1.

{% hint style="danger" %}
If the base style does not have variation Intro B (example), then it’s **not** possible to define Intro B-x in the extension file.
{% endhint %}

### Midi format <a href="#midi-format" id="midi-format"></a>

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
Depending on the CASM data, there might be more than one source phrase for a given instrument (the guitar and guitar\_root phrases in the example above). For example one channel can be used for major chords, the other one for minor chords.
{% endhint %}

A track should only contain Midi note on/off messages for its **source chord** and **source Midi channel,** as defined in the CASM data of the base style. If you used the **Extended style creation wizard**, you have the **source chord** and **Midi channel** indicated in the `<id string>`, as explained above.

### Alternate source phrases <a href="#alternate-takes" id="alternate-takes"></a>

To add **alternate source phrases** for a given variation, just append source phrases on each track of this variation. Each appended source phrase must have the same length than the original phrase.

**Example**\
The source phrase length of track Main A-1-bass-8 is 8 beats (2 bars in 4/4). You can append 2 similar 8-beat source phrases on that track, so the track length becomes 24 beats. YamJJazz will consider the 2 appended phrases as **alternate source phrases** of the first source phrase, to be used randomly when rendering the Main A-1 bass part.&#x20;

Note that 2 alternate source phrases must be also added for all the other Main A-1 tracks: Main A-1-drums-8, Main A-1-guitar-8 and Main A-1-guitar\_root-8.

{% hint style="info" %}
If you have for example 3 source phrases for Main A-1, JJazzLab will randomly pick a source phrase every 2 bars. The selection is actually not 100% random: the first source phrase has more chances to be selected than the second one, and the second one has more chances to be selected than the third one, etc. In other words the last source phrase has the least chances to get selected.
{% endhint %}
