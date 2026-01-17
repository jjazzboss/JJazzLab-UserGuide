---
内容：>-
  JJazzLabは、メニューの「ファイル/ソングをインポート...」を使用すると、異なるファイル形式の曲をインポートできます。
---

# ソングのインポート

## バッチ変換モード

インポートするファイルが多数ある場合は、**バッチ変換モード(Batch convert mode)** を使用してください。このモードでは、インポートしたファイルをJJazzLabで開かずに、直接インポートして.sngファイルに変換します。作成された.sngファイルは、インポートしたファイルと同じディレクトリに保存されます。

**バッチ変換モード**を有効にするには、以下の図のように**「ファイルからソングをインポートする」**ダイアログで対応するチェックボックスを選択してください：

<figure><img src="../.gitbook/assets/2024-12-30 11_57_22-JJazzLab  4.1.2.png" alt=""><figcaption></figcaption></figure>

## Band In A Box楽曲ファイル(.SGU 等)

JJazzLabは.SG\*または.MG\*形式の楽曲ファイルをインポートできます。

以下のBand-In-A-Boxデータのみを使用して、対応するJJazzLab楽曲を生成します：

* **song structure**: コーラス開始、コーラス終了、コーラス回数、タグ後、タグ開始、タグ終了、2小節エンディング
* **chord symbols**: 名前、位置（オプションの強調設定を含む）、休符/持続/ショット設定
* **song settings**: 最初のコーラス/中間のコーラス/最後のコーラスで強調/休符を許可する。

楽曲のインポート機能は100%確実ではありませんが、ほとんどのファイルは問題ないはずです。

{% hint style="danger" %}
**デフォルトでは、インポートされた楽曲は4/4拍子になります**。インポートした楽曲が3/4拍子と分かっている場合は、インポート完了後、最初の拍子記号を選択し、右クリックメニューの**拍子記号を設定**を使用して拍子記号を修正してください。
{% endhint %}

## musicXMLファイル (.xml, .mxl, musicxml)

JJazzLabはMusicXML（.xml、.musicxml）または圧縮MusicXML（.mxl）をインポートできます。iRealProからエクスポートしたMusicXMLファイルでの動作確認が成功しています。&#x20;

インポートされるもの： &#x20;

* コード記号
* 拍子記号
* **direction/direction-type/rehearsal**要素内に存在する「INTRO」、「A」、「B」などのセクションタイトル。
* 繰り返し記号（1. 2. 3...）、終止記号、to coda、coda、segno、DC al coda、DC al fine、DS al coda、DS al fine、**sound**および**barline**要素に存在するもの。
* **play/other-play element** の **groove** タイプに含まれる音楽スタイル情報。



## Text files (.txt)

JJazzLab can read chords from text files. 3 formats are supported, GRID-BASED, TIME-BASED, BEAT-BASED.

#### **GRID-BASED: e.g. "| 3/4 Bb7M | D7#5  | Eb7M | Db7#11 |"**

`!` can be used instead of `|`.  `%` repeats the previous bar. Any bar can start with a time signature.

Example:

`|3/4 Bb7M | D7#5  | Eb7M  | Db7#11 |`\
`| Cm7     | G7     | C7M   |       |`\
`|4/4 Fm7  | Gm7 C7 | %     |  F7M  |`

{% hint style="success" %}
This format is compatible with text files exported from **ChordPulse**.
{% endhint %}

#### **TIME-BASED: "pos\_in\_seconds, chord\_symbol"**

The time signature and tempo must be set first so that pos\_in\_seconds can be converted into bar/beat. If not set, the default values are 4/4 and 120bpm.

Example:\
`timeSignature=3/4`\
`tempoBPM=60`\
`0, C`\
`3, F7`\
`4.5, Eb7`\
`6, D7`

#### **BEAT-BASED : "bar, beat, chord-symbol"**

Note that by default bar and beat are expected to be 0-based (first bar of the song is bar 0). You can change that by adding "`useBase1`" at the beginning of the file, then bar and beat are expected to be 1-based.

Example:\
`0, 0, C`\
`1, 0, F7`\
`1, 1.5, Eb7`\
`2, 0, D7`

#### **Other text format information**

* Lines starting with `//` are ignored (comments)
* "`title=My song name`" : if specified the created song will use this title as name
* Accepted delimiter characters are `,` `;` or space or tab (time or beat-based format)



## Impro-Visor leadsheet files (.ls)

JJazzLab can import Impro-Visor (.ls) leadsheet files.&#x20;

The import is limited to the time signatures and chord symbols.

