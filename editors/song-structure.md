# ソングストラクチャー

**ソングストラクチャーエディター**を使用するのは:

* セクションの順序を**ソング構成**として定義する。例：「AABA」または「ヴァース　ヴァース コーラス ヴァース」
* 使用する**リズム**（音楽スタイル）とそのタイミングを選択する
* 楽曲のパートごとに**リズムパラメータ**を調整し、ダイナミクス（例：変化、強弱、ドラムフィル、ミュート楽器など）を取り入れる。

![](../.gitbook/assets/FullSongStructureEditorText.png)

## ソングパート

**ソングパート**は、[コードリードシート](chord-lead-sheet.md)の親**セクション**としてリンクされています。&#x20;

**ソングパートでは、セクションの演奏順序と方法を定義できます。例えば、_ヴァース_と_コーラス_ の2セクションのみのコードリードシートでも、曲は _ヴァース ヴァース コーラス ヴァース コーラス_ の順で再生します。

ソングパートには、**リズム**の名前、および各[**リズムパラメータ**](song-structure.md#rhythm-parameters)の値が設定されます。リズムパラメータを使用すると、ソングパートでリズムをどのように演奏するかを変更できます。

デフォルトでは、ソングパートの名前は親セクションの名前となります。ソングパートの名前を変更した場合、親セクションの名前がその名前の下に表示されます。

{% hint style="info" %}
連続する複数のソングパートが同じ名前を共有する場合、その名前は _最初のソングパートにのみ表示_ され、連続するソングパートには _線が表示_ されます（下図参照）。

この行をクリックすると、関連するすべてのソングパートを選択します。
{% endhint %}

![](../.gitbook/assets/songparts-samename.png)

## 編集

新しいソングパートを追加するには：

* コードリードシートから**セクションをドラッグ**してソングストラクチャーエディタに配置するか、
* 右クリックメニューの**挿入**、または&#x20;
* 既にあるソングパートをコピーする：Ctrlキーを押しながらドラッグ、コピー＆ペースト、または右クリックメニューの**Duplicate**を使用

**マウスでドラッグ**することでソングパートの順序を変更できます（Ctrlキーを押しながらドラッグするとソングパートを複製できます）。コピー/切り取り/貼り付けコマンドも、ソングパートとリズムパラメータの両方で機能します。

ソングパートの**名前**、**リズム**、**パラメータ**の編集は、[マウス](song-structure.md#mouse-shortcuts)または[キーボードショートカット](song-structure.md#keyboard-shortcuts)を使用してソングストラクチャーエディターから直接行うか、[ソングパートエディタ](song-structure.md#song-part-editor)を介して行うことができます.

{% hint style="success" %}
複数のソングパートやリズムパラメータを一括で編集するには：&#x20;

* **Ctrlキー＋クリック** または **Shiftキー＋クリック** で複数の項目を選択&#x20;
* 編集を行う（例：リズムを変更する、強度を上げるなど）

変更は選択したすべての項目に適用されます。
{% endhint %}

現在の選択範囲（ソングパートまたはリズムパラメータ）に対して利用可能なコマンドを表示するには、ポップアップメニュー（Windows/Linuxでは**右クリック**、Macでは**Ctrlキー＋クリック**）を使用してください。以下の2つの画像のように表示されます。

![Song part popup menu](../.gitbook/assets/SongPartPopupMeny.png)

![Rhythm parameter popup menu](../.gitbook/assets/RhythmParameterPopupMenu.png)

ほとんどのリズムパラメータでは、値を編集する**最も簡単な方法**は、**それを選択**し、**マウスホイール**を使用することです。&#x20;

一部のリズムパラメータにはカスタム編集ダイアログが用意されており、以下に示すように呼び出すことができます。

<figure><img src="../.gitbook/assets/2024-01-05 11_27_00-JJazzLab  4.0.2.png" alt=""><figcaption><p>カスタムエディターでのリズムパラメータ</p></figcaption></figure>

{% hint style="success" %}
コピー＆ペーストを使用すると、**リズムパラメータの値を簡単にコピー**できます。&#x20;

あるソングパート（例：上記画像の「>オープンハイハット」）のドラム変換値を他のソングパートに適用したい場合：&#x20;

* ソングストラクチャーエディタで、元のリズムパラメータを選択し、コピー（Ctrl+C）
* 他のソングパートで同じリズムパラメーターを選択（複数選択にはCtrl+クリックまたはShift+クリックを使用）し、貼り付け（Ctrl+V）
{% endhint %}

複数の連続したリズムパラメータを選択した際、リズムパラメータのポップアップメニューにある、値を調整する***Adjust values**サブメニューを使用すると、最初に選択した値と最後に選択した値の間で値を補間できます。以下の例では、テンポを100%から108%まで徐々に増加させるためにこの機能を使用しました。

![](../.gitbook/assets/AdjustRpValues.png)

## ソングパートエディター

ソングパートエディターは、選択したソングパートを編集する追加の方法を提供します。&#x20;

ソングパートエディターを使用してリズムパラメーター（例：ミュートパラメータ）を編集しますが、そのパラメーターはユーザーがリストから1つ以上の値を選択（Ctrlキー＋クリック）する必要があります。
<figure><img src="../.gitbook/assets/2024-01-05 11_37_05-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

## リズムの変更 (音楽スタイル)

各ソングパートごとに独自のリズムを設定できます。&#x20;

{% hint style="warning" %}
MIDIは16チャンネルまでしか対応できず、多くのリズムには7～8種類の楽器が使われています。そのため、2つ以上のリズムを含む楽曲を実際に作成するのは困難です。
{% endhint %}

リズムを変更するには、ソングパートを選択して**R**を押すか、リズム名をクリックして**rhythm selection dialog**を開きます。

![](../.gitbook/assets/RhythmSelectionDialog.png)

リズムを変更する際、JJazzLabは前のリズムパラメータの値を新しいリズムパラメータに適合させようと試みます。

曲の途中でリズムチェンジを削除したい場合は、そのソングパートを選択し、ソングパートのポップアップメニューから**Remove Rhythm Change**を選択してください。

![](../.gitbook/assets/RemoveRhythmChange.png)



## リズムパラメーター

リズムパラメータを使用すると、特定のソングパートにおけるリズム（音楽スタイル）の演奏方法を調整できます。&#x20;

{% hint style="success" %}
リズムパラメーターは、**バッキングトラックに変化を加える**ためのシンプルで強力なツールであり、演奏をより楽しくします。
{% endhint %}

JJazzLabでは、[リズムエンジン](/broken/pages/-MQSAs6SfPTmre5f3rhY)の開発者がカスタムリズムパラメータを定義できます。ただし、リズムエンジンでは以下に説明する共通の標準パラメータセットが頻繁に使用されます。

### バリエーション(Variation)

使用するリズム（スタイル）バリエーションを示すリズムパラメーター。[YamJJazzエンジン](../rhythm-engines/yamjjazz-rhythm-engine/)のリズムには通常、4つの _Main_ バリエーションに加え、いくつかの _Intros_、_Endings_、_Fills_ が存在します。

### 強度(Intensity)

このパラメータは、生成するバッキングトラックの音量を定義します。&#x20;

リズムエンジンはこのパラメータに応じて、単にバッキングトラックの音符のMIDIベロシティを増減させることもあれば、音符の数を増減させるなど、さらに多様な処理を行うことも可能です。

### ドラムフィル

このパラメータは、ソングパートの終わりにドラムフィル（またはブレイク）を再生するかを決めます（_never_、_always_、_randomly_、...）。&#x20;

_fade\_out_ 値は特別で、ドラムフィルを生成せず、代わりにソングパートの終わりまで音符のベロシティを徐々に減少させます。

### ミュート

このパラメーターは、このソングパートにおいて1つ以上の楽器をミュートするために使用されます。このパラメータを編集するには、 **[ソングパートエディター ]**(song-structure.md#song-part-editor)を使用すると簡単です。

### **マーカー**

このパラメータは、[こちら](chord-lead-sheet.md#substitute-chord-symbol)で説明されている代替コード記号を使用する場合にのみ有用です。

### テンポ要素

このパラメーターを使用して、ソングパートのテンポを遅くしたり速くしたりできます。

### ドラムの変換

このパラメータを使用すると、ソングパートのドラム音符の一部を変更できます。&#x20;

これは**ドラムトラックを簡単に変更する**方法で、楽曲にバリエーションを加えることができます。&#x20;

例えば、ハイハットの音量を上げたり、クローズドハイハットをライドシンバルに変えたり、単にパーカッションを追加したりできます！

![](../.gitbook/assets/DrumsTransform.png)

### カスタムフレーズ

このパラメータを使用すると、ソングパートの1つ以上の楽器フレーズをカスタマイズできます。\
&#x20;\
例：2番のサビの終わりにあるベースフレーズを変更したい場合\
&#x20;\
対応するソングパートのカスタムフレーズリズムパラメーターを編集した後、ベーストラックを編集します。デフォルトのベースフレーズが[ノートエディター](notes-editor.md)に表示され、変更が可能になります。 \
\
このカスタマイズしたベースフレーズを曲の最後のヴァースでも使用したい場合は、[リズムパラメータの値をコピー](song-structure.md#editing)し、最後のソングパートに貼り付けてください。

![](<../.gitbook/assets/2024-01-05 11_52_05-Customize phrases for song part _A_ - bars 1..8 (1).png>)

### Track overrides

This parameter lets you use one or more tracks from other rhythms.

_Example: your song uses a 8-beat pop rhythm. You want to spice up the chorus song part and use **Track overrides** to replace the 8-beat original bass line by the bass line from a bossa-nova rhythm._

<figure><img src="../.gitbook/assets/TrackOverride.png" alt=""><figcaption></figcaption></figure>

Other usage examples:

* You like a jazz Yamaha style except the bass line which does not sound good. Use the Track overrides parameter to replace the bass line by [jjSwing](../rhythm-engines/jjswing-rhythm-engine.md)'s realistic walking bass.&#x20;
* The override rhythm can be the same than the original rhythm. For example this lets you override the piano part by the bass part from the same rhythm, so that the bass line is doubled piano+bass on a given song part.&#x20;

### Compact / full view

By default only a subset of the rhythm parameters are visible, this is the **compact view**.&#x20;

Click on the button below or press 'V' to switch between compact and full view.

![](../.gitbook/assets/CompactView.png)

The **compact view settings** button, just above the compact view button, lets you choose which rhythm parameters are visible in the compact view. These settings are saved with the song.

<figure><img src="../.gitbook/assets/2024-01-05 22_43_31-Compact view settings.png" alt=""><figcaption><p>Compact view settings</p></figcaption></figure>

As a shortcut, you can directly hide a rhythm parameter (i.e. make it non visible in the compact view) by clicking on the X button in the upper left corner, as shown below.

<figure><img src="../.gitbook/assets/QuickHideRp.png" alt=""><figcaption></figcaption></figure>

## Mouse shortcuts

<table data-header-hidden><thead><tr><th width="253.33333333333331">Selection</th><th>Mouse</th><th>Action</th></tr></thead><tbody><tr><td>Selection</td><td>Mouse</td><td>Action</td></tr><tr><td>song part, rhythm param.</td><td>click</td><td>select</td></tr><tr><td>song part</td><td>double click</td><td>edit song part name</td></tr><tr><td>song part name</td><td>click</td><td>edit </td></tr><tr><td>rhythm</td><td>click</td><td>select a rhythm</td></tr><tr><td>editor, song part, rhythm param.</td><td>right-click</td><td>open popup menu</td></tr><tr><td>rhythm parameter</td><td>double-click</td><td>edit value</td></tr><tr><td>rhythm parameter</td><td>mouse wheel</td><td>change value</td></tr><tr><td>rhythm parameters</td><td>shift+mouse wheel</td><td>make values identical then change value</td></tr><tr><td>editor</td><td>ctrl mouse wheel</td><td>change X zoom factor</td></tr></tbody></table>

## Keyboard shortcuts

{% hint style="info" %}
Many actions are also available via the context menu (right-click on Windows/Linux, ctrl-click on Mac), and when available the associated shortcut is displayed.
{% endhint %}

| Selection                | Key                    | Action                   |
| ------------------------ | ---------------------- | ------------------------ |
| song part, rhythm param. | enter                  | edit song part name      |
| song part, rhythm param. | R                      | select rhythm            |
| song part, rhythm param. | I                      | insert song part         |
| song part, rhythm param. | ctrl-I                 | append song part         |
| song part, rhythm param. | D                      | duplicate song part(s)   |
| song part                | delete                 | delete song part(s)      |
| rhythm parameter         | ctrl-up/down           | next/previous value      |
| rhythm parameter         | Z                      | reset param. value       |
| song part                | ctrl-C/X/V             | copy/cut/paste           |
| editor                   | ctrl-Z/Y               | undo/redo                |
| editor                   | ctrl-F                 | zoom to fit width        |
| editor                   | V                      | compact or full view     |
| editor                   | ctrl mouse-wheel       | zoom in/out horizontally |
| editort                  | ctrl+shift mouse-wheel | zoom in/out vertically   |
