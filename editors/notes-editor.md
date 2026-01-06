# ノートエディター

JJazzLabにはMIDIノートエディタが組み込まれており、[**ユーザートラック編集**](notes-editor.md#edit-a-user-track) や [**ソングパートのカスタムフレーズ編集**](notes-editor.md#edit-a-custom-phrase-for-a-song-part)で使用します。

<figure><img src="../.gitbook/assets/2024-12-30 11_01_51-JJazzLab  4.1.2.png" alt=""><figcaption><p>メロディトラック</p></figcaption></figure>

<figure><img src="../.gitbook/assets/2024-01-01 00_06_53-JJazzLab  4.0.2.png" alt=""><figcaption><p>ドラムトラック</p></figcaption></figure>

<figure><img src="../.gitbook/assets/2024-12-30 13_30_36-JJazzLab  4.1.2.png" alt=""><figcaption><p>簡略化されたスコア</p></figcaption></figure>

{% hint style="warning" %}
現時点では、スコアパネル（上記）は**簡略化された楽譜表記**を使用しています：音符の位置はエディタの音符と一致するように揃えられており、装飾は一切ありません。スコアパネルは編集できません。&#x20;
{% endhint %}

## ノートエディタを開く

### ユーザートラック編集

ノートエディターは、[ユーザートラックを追加](mix-console.md#adding-user-tracks)すると、自動的に開きます。 既存のユーザートラックについては、下記に示すようにトラック概要コンポーネント内の編集ボタンをクリックしてください。&#x20;

<figure><img src="../.gitbook/assets/2023-12-31 22_02_16-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

リズムトラックは、最初にユーザートラックとして複製した後で、ノートエディタで編集することもできます：

<figure><img src="../.gitbook/assets/2023-12-31 21_58_28-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

### ソングパートのカスタムフレーズ編集

ソングストラクチャーエディターで、カスタムフレーズリズムパラメータの左上ボタンをクリックしてください:

<figure><img src="../.gitbook/assets/2024-01-05 12_40_44-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

次に、カスタマイズしたいフレーズを選択し、「編集」を押してノートエディターを開きます。

<figure><img src="../.gitbook/assets/2024-01-05 11_52_05-Customize phrases for song part _A_ - bars 1..8 (1).png" alt=""><figcaption></figcaption></figure>

## 移動とズーム

下図のように、上部のルーラー上で**Ctrlキー＋ドラッグ**するとエディタを移動できます:

<figure><img src="../.gitbook/assets/2024-01-01 00_12_51-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

メインアプリケーションの右下隅にあるズームスライダーを使用するか、水平方向のズームには**Ctrlキー＋マウスホイール**、垂直方向のズームには**Ctrlキー＋Shiftキー＋マウスホイール**を使用できます。&#x20;

**Ctrl+F** キーで幅に合わせて拡大表示します。

<figure><img src="../.gitbook/assets/2023-12-31 23_37_35-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

## 再生コントロール

以下の画像に示すツールバーボタンを使用するか、**Ctrl+Shift+スペース**を押して、編集したフレーズ、または設定されている場合は[再生ループゾーン](notes-editor.md#playback-loop-zone)を**ループ再生モード**で再生します。

<figure><img src="../.gitbook/assets/2024-05-16 22_49_35-JJazzLab  4.0.3-SNAPSHOT.png" alt=""><figcaption><p>再生開始ボタン</p></figcaption></figure>

**Ctrl+スペース**を押して再生を開始 :

* 設定されている場合、[再生ループゾーン](notes-editor.md#playback-loop-zone) から
* 最初の選択された音符の小節から
* 音符が選択されていない場合、最初に見える小節から

その他のコントロール:

<div>
  <figure><img src="../.gitbook/assets/NoteEditor-soloButton.png" alt=""><figcaption><p>編集したフレーズのみを聴く</p></figcaption></figure>
  <figure><img src="../.gitbook/assets/NoteEditor-autoscroll.png" alt=""><figcaption><p>再生中に自動スクロールする</p></figcaption></figure> 
  <figure><img src="../.gitbook/assets/NoteEditor-Hear.png" alt=""><figcaption><p>選択した音符を聴く</p></figcaption></figure>
</div>

### 再生ループゾーン

再生ループゾーンは、上部の**ルーラー**上で**マウスドラッグ**により設定できます。ルーラー上で**Shiftキー＋クリック**するとループゾーンを拡張できます。ルーラー上で**クリック**するとループゾーンを解除できます。

<figure><img src="../.gitbook/assets/2024-05-16 22_47_02-JJazzLab  4.0.3-SNAPSHOT.png" alt=""><figcaption></figcaption></figure>

ツールバーのボタン（上記参照）または **Ctrl+Shift+スペース** キーを押して、ループゾーンの再生を開始します。

## グリッドにスナップ

**Snap to grid**ボタン（または**G**キーを押す）を使用すると、音符の描画/移動/サイズ変更時にグリッドにスナップできます。グリッドのサイズはドロップダウンリスト(1/4=四分音符, 1/8=八分音符, ...)で設定可能です。 :

<figure><img src="../.gitbook/assets/2023-12-31 23_20_16-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Select tool**で音符の移動やサイズ変更を行う際、**alt**キーを押すと一時的に「グリッドにスナップ」設定を無効にできます.
{% endhint %}

既存の音符の位置を変更するには、[Quantize](notes-editor.md#quantize-notes)を使います。

## 編集ツール

ノートを編集するには3つのツールが使用できます：**選択（select)ツール**、**描画(draw)ツール**、**消去(erase)ツール**。最初の2つの編集ツールは[グリッドにスナップ](notes-editor.md#snap-to-grid)設定の影響を受けます。.

ツールは、ノートエディターのトップツールバーにあるボタンから選択するか、エディター内で右クリックすることで選択できます。:

<figure><img src="../.gitbook/assets/2023-12-31 23_14_25-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

**選択ツール**を使用して、音符の選択、移動、サイズ変更、コピー/切り取り（**Ctrl+C/X**）、削除（**Delete**キーを押す）を行います。&#x20;

**Ctrl+V** キーで音符を貼り付けますs.

{% hint style="danger" %}
音符を貼り付ける位置をコントロールする方法とは？

* 音符を選択している場合、最初に貼り付けた音符はその選択している音符に揃います
* 音符を選択していない場合、最初に貼り付けた音符はノートエディタの左側に揃えられます

新しく貼り付けたメモは自動的に選択されるため、必要に応じて適切な位置に移動できます。
{% endhint %}

**Drag** to select several notes. Use **ctrl-drag** notes to duplicate notes. **ctrl-shift-I** invert the notes selection.

<figure><img src="../.gitbook/assets/2023-12-31 23_25_52-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

Use the **draw tool** to draw notes, and the **erase tool** to erase notes.

<figure><img src="../.gitbook/assets/2024-01-01 00_16_08-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

## Changing notes velocity

Notes color vary with their velocity. There are several way to change notes velocity, as shown below.

#### Using the main editor panel

First select the notes to change. Then either use the velocity spinner in the toolbar, or use **alt + mouse-wheel** or **alt + page up/down**.

<figure><img src="../.gitbook/assets/2023-12-31 23_29_11-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

#### Using the velocity panel

**Click** or **mouse-drag** on notes to adjust their velocity.

<figure><img src="../.gitbook/assets/2024-12-30 11_04_48-JJazzLab  4.1.2.png" alt=""><figcaption></figcaption></figure>

## Quantize & humanize notes

Use the **Quantize** button or press **Q** to move the selected notes start position on the current grid. If no note selected, all notes are quantized.

Check the **Iterative** box to perform iterative quantize : notes are gradually moved towards the grid. This is usually recommended to avoid a too mechanical sound.

<figure><img src="../.gitbook/assets/2024-01-01 00_28_31-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

You can also **humanize** all or selected notes. Humanization introduces slight random variations in the notes start position and velocity. Use the **Humanize** button on the left, or press **ctrl-H** to show the Humanize dialog.

<figure><img src="../.gitbook/assets/2024-05-16 23_10_38-JJazzLab  4.0.3-SNAPSHOT.png" alt=""><figcaption></figcaption></figure>

Once you clicked the Humanize button, you can adjust the humanization parameters and see the different results.

#### Example

This bass line is very uniform: all notes have the same velocity and are quantized. This sounds too "robotic".

<figure><img src="../.gitbook/assets/2024-12-30 11_40_40-JJazzLab  4.1.2.png" alt=""><figcaption></figcaption></figure>

We can use the Humanize dialog to improve this, as shown below.

<figure><img src="../.gitbook/assets/2024-12-30 11_41_33-JJazzLab  4.1.2.png" alt=""><figcaption></figcaption></figure>

## Importing notes

You can import notes by dragging an external Midi file into the editor. You can also drag from an individual track in the mix console.

<figure><img src="../.gitbook/assets/2023-12-31 22_54_43-JJazzLab  4.0.2.png" alt=""><figcaption><p>Importing a Midi file in the editor</p></figcaption></figure>

{% hint style="warning" %}
If the imported Midi file contains notes from several Midi channels, then JazzLab **only imports the notes which match the editor Midi channel.**&#x20;

If the imported Midi file only contains notes from a single channel, then JJazzLab imports the notes with the channel updated to the editor Midi channel.
{% endhint %}

## Mouse shortcuts

<table data-header-hidden><thead><tr><th width="253.33333333333331">Selection</th><th>Mouse</th><th>Action</th></tr></thead><tbody><tr><td>Notes</td><td>ctrl-click </td><td>select multiple notes</td></tr><tr><td>Editor</td><td>drag</td><td>select multiple notes</td></tr><tr><td>Notes</td><td>drag</td><td>move/resize</td></tr><tr><td>Notes</td><td>ctrl-drag</td><td>duplicate notes</td></tr><tr><td>Notes</td><td>alt-drag</td><td>move/resize with snap-to-grid setting reversed</td></tr><tr><td>Notes</td><td>alt-wheel</td><td>change velocity</td></tr><tr><td>Editor</td><td>wheel</td><td>move editor up down</td></tr><tr><td>Editor</td><td>shift mouse-wheel</td><td>movbe editor left right</td></tr><tr><td>Editor</td><td>ctrl mouse-wheel</td><td>zoom in/out horizontally</td></tr><tr><td>Editor</td><td>ctrl-shift mouse-wheel</td><td>zoom in/out vertically</td></tr><tr><td>Editor</td><td>ctrl-drag</td><td>Move editor</td></tr><tr><td>Ruler</td><td>drag</td><td>set playback loop zone</td></tr><tr><td>Ruler</td><td>shift-click</td><td>extend playback loop zone</td></tr><tr><td>Ruler</td><td>click</td><td>remove playback loop zone</td></tr></tbody></table>

## Keyboard shortcuts

| Selection | Key              | Action                                                   |
| --------- | ---------------- | -------------------------------------------------------- |
| Notes     | alt-up/down      | change velocity                                          |
| Notes     | ctrl-C/X/V       | copy/cut/paste notes                                     |
| Notes     | delete           | delete notes                                             |
| Notes     | ctrl-shift-I     | invert notes selection                                   |
| Notes     | ctrl-H           | open humanize dialog                                     |
| Notes     | Q                | quantize selected notes (or all no selection)            |
| Editor    | ctrl-F           | zoom to fit notes                                        |
| Editor    | G                | snap-to-grid                                             |
| Editor    | A                | auto-scroll during playback                              |
| Editor    | S                | solo the edited phrase                                   |
| Editor    | H                | hear the selected notes                                  |
| Editor    | Home/End         | Move editor to start/end                                 |
| Editor    | ctrl-shift-space | play the loop zone (if set) or whole phrase              |
| Editor    | ctrl-space       | play from loop zone (if set) or from first selected note |
| Editor    | ctrl-Z/Y         | undo/redo                                                |
