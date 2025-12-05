# コード譜

**コード譜エディター**の使い方：

* コード記号を書く、例 **Cm6, Ab7, F#9M#11, NC (コード無し) ...**
* セクション記号を書く、例 **A, B, verse, chorus,**
* コード記号をずらしたり編集して、リズムのアクセントや、解釈(interpretation)や、ハーモニーに合わせる
* 小節に注意書きを書く(歌詞等のため)

![](../.gitbook/assets/ChordLeadSheetText.png)

## ポップアップメニュー

現在の選択範囲（小節線、和音記号、またはセクション）に対して利用可能なコマンドを表示するには、ポップアップメニュー（Windows/Linuxでは**右クリック**、Macでは**Ctrlキーを押しながらクリック**）を使用してください。

![Bar popup menu](../.gitbook/assets/BarPopupMenu.png)

![Chord symbol popup menu](../.gitbook/assets/chordPopupMenu.png)

![Section/Time signature popup menu](../.gitbook/assets/sectionPopupMenu.png)

## コード記号の選択と移動

小節またはコード記号をクリックして選択します。**Ctrlキーを押しながらクリック**すると、複数の小節またはコード記号を選択できます。&#x20;

**Shiftキーを押しながらクリック**すると、現在の選択範囲を拡張します。

コード記号をマウスで**ドラッグ**すると、新しい位置に移動できます。ドラッグ中に**Ctrl**キーを押すと、**+**記号が表示され（下図参照）、コード記号が移動ではなくコピーされることを示します。

<figure><img src="../.gitbook/assets/dragCopyChord.png" alt=""><figcaption></figcaption></figure>

#### コード記号のクオンタイズ

デフォルトでは、コード記号の位置は16分音符単位（1拍あたり4つ）でクォンタイズされます。&#x20;

これは、以下の図に示すように、小節またはセクションのポップアップメニュー **Quantization...** からセクションごとに調整できます。

<figure><img src="../.gitbook/assets/ChordQuantizeMenu.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/ChordQuantizeDialog.png" alt=""><figcaption></figcaption></figure>

**auto**値は、このセクションにリンクしている最初のソングパートで使用するリズム（二拍子または三拍子）に基づいてクオンタイズを調整します。

## コード記号の入力

小節またはコード記号を選択し、コード記号の最初の文字（例：'C'）を入力すると、**小節編集ダイアログ**が自動的に表示されます：

<figure><img src="../.gitbook/assets/2024-04-26 22_32_35-Bar 3 - A 4_4.png" alt=""><figcaption><p>Bar edit dialog</p></figcaption></figure>

小節を選択した状態で、**小節編集ダイアログ**は、Enterキーを押す、小節をダブルクリックする、または右クリックメニューを使用することで表示できます。

コード記号を**コピー**するには、**ctrl**キーを押しながら**ドラッグ**してください。

{% hint style="info" %}
**リードシートを一から入力する**には、最初の小節を選択し、コード記号を直接入力するのが最も簡単な方法です（最初の文字を入力すると小節編集ダイアログが自動的に表示されます）。入力完了後、Enterキーを押すと（自動的に次の小節が選択されます）、2小節目のコード記号を入力し、同様に続けます。
{% endhint %}

JJazzLabは、コード記号をいろいろな表記形式で認識できます。例えば、**C-7**、**Cm7**、**Cmi7**、**Cmin7**はすべて同じです。ツール/設定の**chord symbol**タブで、以下に示すように独自の_コード記号の別名_を追加できます：

<figure><img src="../.gitbook/assets/2024-03-06 19_22_02-Options.png" alt=""><figcaption><p>独自のコード記号(aliases)を定義する</p></figcaption></figure>

{% hint style="info" %}
**NC**コード記号は特別で、これを使用すると次のコード記号まで無音にできます。完全な無音が長すぎる場合は、**shot**付きのコード記号を試してみてください。[表現解釈](chord-lead-sheet.md#interpretation).
{% endhint %}

## カスタマイズ可能なコード進行

小節を選択し、ポップアップメニューの **挿入/Chord progression** から挿入するコード進行を選択してください。

<figure><img src="../.gitbook/assets/InsertChordprogression.png" alt=""><figcaption></figcaption></figure>

コード進行は選択した小節に挿入され、既存のコードを置き換えます。必要に応じて追加の小節が生成されます。挿入されたコードは自動的に選択されるため、目的の調へ簡単に移調できます（コード上でマウスホイールを使用するか、Ctrlキー＋上/下矢印キーを押してください）。

コード進行は、JJazzLabのユーザーディレクトリ内にあるシンプルなテキストファイル`ChordProgression.txt`で定義されます。このファイルは存在しない場合、JJazzLabによって自動的に作成されます。

**Chord progression...** からポップアップメニュー（上記画像参照）した **Open configuration file...** を選択すると編集できます。これにより、ポップアップメニューに表示されるコード進行を定義・整理できます。

## Changing the size of the leadsheet

Select a bar then select **Set end bar** in the right-click menu (see below).

{% hint style="info" %}
The size of the song depends on both the leadsheet _and_ the song structure.&#x20;

For example, if chord leadsheet only contains a single 12-bar section called A, and song structure is A-A-A, then song size is 3\*12=36 bars.
{% endhint %}

## Interpretation

Select a chord symbol, edit it (double-click, press enter, or right-click menu), and select the **Interpretation** tab.

![](../.gitbook/assets/chordsymbolinterpretationdialog.png)

The **Interpretation** tab lets you decide how this chord symbol should be played:

* **Normal**
* **Accent**: add a rhythmic accent and randomly a crash cymbal. You can make the accent stronger, or make sure a crash cymbal is played or not played.
* **Hold**: add a rhythmic accent and hold notes until next chord symbol. If extended more instruments are hold.
* **Shot**: add a rhythmic accent with chord notes played briefly. If extended more instruments are shot.
* **Pedal bass**: bass line will only play the bass note (for ex. F for Fm7 or C for Fm7/C). This setting is on by default when you enter a slash chord.

{% hint style="info" %}
Each rhythm generation engine may render these Interpretation parameters differently.
{% endhint %}

\
&#x20;The shape of the marker below the chord symbol depends on the interpretation mode:

![](../.gitbook/assets/interpretationmarkers.png)

&#x20;For example, in order to render:&#x20;

![](../.gitbook/assets/rhythmicaccents.png)

you could use the following interpretation parameters:&#x20;

![](../.gitbook/assets/examplerhythmicaccents.png)

{% hint style="info" %}
See below the keyboard shortcuts to change the interpretation of selected chords.
{% endhint %}

### Harmony

Select a chord symbol, edit it and select the **Harmony** tab.

![](../.gitbook/assets/chordsymbolharmonydialog.png)

The **Harmony** tab lets you select the scale to be used when rendering the music for this chord symbol.

**Example** Suppose that the reference bass line for Eb7M contains a Ab (4th degree of the Eb major scale). If you select the Lydian mode (which has a sharp 11th degree) then the reference bass note Ab will be rendered as A for this chord symbol.

By default no scale is selected: each rhythm generation engine will decide the "best" scale to use.

### Substitute chord symbol

Select a chord symbol, edit it and select the **substitute** chord symbol tab.

![Snapshot to be updated! Alternate > Substitute](../.gitbook/assets/chordsymbolalternatedialog.png)

This tab lets you define a **substitute** chord symbol which will be used when some conditions are met.&#x20;

**Substitute** chord symbols are useful when you need to introduce a slight variation in a part of a song.

The **substitute** chord symbol can be any chord symbol, with any interpretation or harmony, or no chord symbol at all (void chord). Chord symbols which have an **substitute** chord symbol defined are displayed with a different color (see image below).

_Example:_

In the Carlos Santana's "Europa" song, the 1st ending of the theme is a Cm7, but the 2nd one is a C major. To implement this in JJazzLab, one solution could be to duplicate section A1 to create section A2 with the different ending, then update the song structure accordingly. This is perfectly fine, but when changes are minor the **substitute** chord symbol can provide a simpler solution.

You can see below (and in the dialog snapshot above) that a C7M **substitute** chord has been created for Cm7. C7M will be used for all song parts (see the [song structure editor](song-structure.md)) where the marker is set to Theme2. On the image below it means the C7M will be used only for the 2nd song part.

![Snapshot to be updated! ALTERNATE > SUBSTITUTE](../.gitbook/assets/alternatechordleadsheet.png)

There is another **substitute** chord symbol example in the 3rd bar: A7. If you listen to the original song you'll notice that they play a A7 on the last beat of the 3rd bar only during solos. So the A7 chord symbol defines its **substitute** chord symbol as the "void chord symbol" (same as no chord symbol) when marker is _not_ "Solo".

## Sections input

Typical sections are 'intro', 'verse', 'chorus', etc.

A Song section is the basic unit used by JJazzLab to define the song structure. There is always a section defined on the first bar.

To add a section select a bar which is not after the end then:

* press ENTER, or
* double-click, or
* right-click menu, Insert Section... or Edit...

{% hint style="warning" %}
Section names must be unique.
{% endhint %}

### Force a section at new line

You can force a section which is not on the first bar of a row to start on the next line. This can be useful when some sections have an odd number of bars.

Select a bar with a section defined or select the section itself, right-click menu "Force Section at New Line".

![](../.gitbook/assets/forcesectionnewline1.png)

&#x20; This will result in the display below.&#x20;

![](../.gitbook/assets/forcesectionnewline2.png)

## Bar annotations / lyrics

You can add annotations to any bar.&#x20;

<figure><img src="../.gitbook/assets/2024-01-01 00_35_05-Chord lead sheet - English — Mozilla Firefox.png" alt=""><figcaption></figcaption></figure>

When annotations are hidden, bar with annotations are marked with a post-it (tooltip shows the annotation text).

<figure><img src="../.gitbook/assets/2024-01-01 00_42_01-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

#### Special # syntax for Easy Reader

Suppose the same bar is used in different song parts. The lyrics for this bar might change depending on the song part. You can prepend **#** to annotation lines so that the [Easy Reader](../tools/easy-reader.md) displays only the relevant line.

<figure><img src="../.gitbook/assets/2024-01-01 01_07_05-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

**Example**:  for the annotation above, Easy Reader will show "with... you" the first time, "and...you" the second time, and "take...you" whenever the current song part name is "chorus".

## Exporting/importing chord leadsheet as text

Select some bars or chord symbols and copy them (via menu Copy or ctrl-C/command-C). Then switch to any text editor and paste : the bars/chords are exported as text like below:

`|4/4 Bb9 A7 | Dm7 G13 | Dm7 G13 | Dm7 G13 |` \
`| Gm7/Bb     | C9/Bb  |  F7M    |          |`

Text import works the other way around. Copy a similar text in the clipboard then paste it in the chord leadsheet editor: the correspondings bars/chord symbols are imported in the JJazzLab song.

## Mouse shortcuts

| <mark style="background-color:blue;">**Selection**</mark> | <mark style="background-color:blue;">**Mouse**</mark> | <mark style="background-color:blue;">**Action**</mark> |
| --------------------------------------------------------- | ----------------------------------------------------- | ------------------------------------------------------ |
| bar, chord symbol, section                                | click                                                 | select                                                 |
| chord symbol                                              | double click                                          | edit using chord symbol editor                         |
| chord symbol                                              | ctrl-shift click                                      | hear the chord                                         |
| bar, section                                              | double click                                          | edit using bar editor                                  |
| bar, chord symbol, section                                | right-click                                           | popup menu                                             |
| chord symbol                                              | mouse-wheel                                           | transpose                                              |
| editor                                                    | ctrl mouse-wheel                                      | zoom in/out horizontally                               |
| editor                                                    | ctrl-shift mouse-wheel                                | zoom in/out vertically                                 |

## Keyboard shortcuts

{% hint style="info" %}
Many actions are also available via the context menu (right-click on Windows/Linux, ctrl-click on Mac), and when available the associated keyboard shortcut is displayed.
{% endhint %}

| Selection                  | Key             | Action                                    |
| -------------------------- | --------------- | ----------------------------------------- |
| chord Symbol               | enter           | edit with chord symbol editor             |
| bar, section               | enter           | edit with bar editor dialog               |
| bar                        | ctrl-E          | set end bar                               |
| bar                        | I               | insert bars                               |
| bar                        | delete          | clear bar contents                        |
| chord symbol, section      | delete          | remove                                    |
| chord symbol, section      | ctrl-left/right | move item one bar left/right              |
| bar                        | shift-delete    | remove                                    |
| chord symbol               | ctrl-up/down    | transpose                                 |
| chord symbol               | P               | change interpretation                     |
| chord symbol               | S               | stronger accent                           |
| chord symbol               | H               | crash cymbal/no crash                     |
| chord symbol               | X               | hold/shot more instruments                |
| chord symbol               | M               | hear the chord                            |
| chord symbol, section      | ctrl-A          | select all in section, then in lead sheet |
| bar, chord symbol, section | ctrl-C/X/V      | copy/cut/paste items                      |
| editor                     | ctrl-Z/Y        | undo/redo                                 |
| editor                     | ctrl-L          | Show/hide bar annotations                 |
| editor                     | alt-L           | Insert bar annotation                     |
| editor                     | ctrl-W          | close song                                |
