# Notes editor

JJazzLab embeds a Midi notes editor which is used to edit [**user tracks**](mix-console.md#user-tracks) or [**song part custom phrases**](notes-editor.md#edit-a-custom-phrase-for-a-song-part)**.**

<figure><img src="../.gitbook/assets/2023-12-31 23_11_42-JJazzLab  4.0.2.png" alt=""><figcaption><p>Melodic track</p></figcaption></figure>

<figure><img src="../.gitbook/assets/2024-01-01 00_06_53-JJazzLab  4.0.2.png" alt=""><figcaption><p>Drums track</p></figcaption></figure>

## Opening the notes editor

### Edit a user track

Click the edit button in the track overview component of a [user track](mix-console.md#user-tracks) to open the notes editor :

<figure><img src="../.gitbook/assets/2023-12-31 22_02_16-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

Rhythm tracks can also be edited by cloning them first as a user track :

<figure><img src="../.gitbook/assets/2023-12-31 21_58_28-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

### Edit a Custom phrase for a song part

In the song structure editor, click the top-left button of a Custom phrase rhythm parameter:

<figure><img src="../.gitbook/assets/2024-01-05 12_40_44-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

Then select the phrases you wish to customize and press Edit to open the notes editor.

<figure><img src="../.gitbook/assets/2024-01-05 11_52_05-Customize phrases for song part _A_ - bars 1..8 (1).png" alt=""><figcaption></figcaption></figure>

## Moving and zooming

You can move the editor by dragging the position line as show below:

<figure><img src="../.gitbook/assets/2024-01-01 00_12_51-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

You can use the main application zoom sliders in the lower right corner, or use **ctrl+mouse-wheel** for horizontal zoom, **ctrl+shift+mouse-wheel** for vertical zoom.&#x20;

Use **ctrl-F** to zoom to fit width.

<figure><img src="../.gitbook/assets/2023-12-31 23_37_35-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

## Snap to grid

Use the **Snap to grid** button (or press **G**) to snap notes to the grid. The size of the grid can be set using the drop-down list:

<figure><img src="../.gitbook/assets/2023-12-31 23_20_16-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
When you move or resize notes with the **Select tool**, you can temporarily reverse the "snap to grid" setting by pressing **alt**.
{% endhint %}

## Edit tools

You can use 3 tools to modify notes: **select tool**, **draw tool**, **erase tool**.&#x20;

Tools can be selected using buttons from the notes editor top toolbar, or by right-clicking in the editor:

<figure><img src="../.gitbook/assets/2023-12-31 23_14_25-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

Use the **select tool** to select, move, resize, copy (ctrl-C), delete notes (press delete). Drag to select several notes.

<figure><img src="../.gitbook/assets/2023-12-31 23_25_52-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

Pasted notes are positionned from the first visible position in the editor, or from the first selected note if any.

Use the **draw tool** to draw notes, and the **erase tool** to erase notes.

<figure><img src="../.gitbook/assets/2024-01-01 00_16_08-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

## Changing notes velocity

First select the notes to change. Then either use the velocity spinner in the toolbar, or use **alt + mouse-wheel** or **alt + page up/down**.

<figure><img src="../.gitbook/assets/2023-12-31 23_29_11-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

## Quantifier

Use the **Quantify** button or press **Q** to quantify the selected notes (or all the notes if no note selected) on the current grid.

Check the **Iterative** box to perform iterative quantification (notes move gradually towards the grid).

<figure><img src="../.gitbook/assets/2024-01-01 00_28_31-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

## Importing notes

You can import notes by dragging an external Midi file into the editor. You can also drag from an individual track in the mix console.

<figure><img src="../.gitbook/assets/2023-12-31 22_54_43-JJazzLab  4.0.2.png" alt=""><figcaption><p>Importing a Midi file in the editor</p></figcaption></figure>

{% hint style="warning" %}
If the imported Midi file contains notes from several Midi channels, then JazzLab **only imports the notes which match the editor Midi channel.**&#x20;

If the imported Midi file only contains notes from a single channel, then JJazzLab imports the notes with the channel updated to the editor Midi channel.
{% endhint %}

## Mouse shortcuts

<table data-header-hidden><thead><tr><th width="253.33333333333331">Selection</th><th>Mouse</th><th>Action</th></tr></thead><tbody><tr><td>Notes</td><td>ctrl-click </td><td>select multiple notes</td></tr><tr><td>Editor</td><td>drag</td><td>select multiple notes</td></tr><tr><td>Notes</td><td>drag</td><td>move/resize</td></tr><tr><td>Notes</td><td>alt-drag</td><td>move/resize with snap-to-grid setting reversed</td></tr><tr><td>Notes</td><td>alt-wheel</td><td>change velocity</td></tr><tr><td>Editor</td><td>wheel</td><td>move editor up down</td></tr><tr><td>Editor</td><td>shift-wheel</td><td>movbe editor left right</td></tr><tr><td>Editor</td><td>ctrl-wheel</td><td>zoom horizontally</td></tr><tr><td>Editor</td><td>ctrl-shift-wheel</td><td>zoom vertically</td></tr><tr><td>Editor</td><td>right-click</td><td>select edit tool</td></tr></tbody></table>

## Keyboard shortcuts

| Selection | Key            | Action                      |
| --------- | -------------- | --------------------------- |
| Notes     | alt-up/down    | change velocity             |
| Notes     | ctrl-C/X/V     | copy/cut/paste notes        |
| Notes     | delete         | delete notes                |
| Editor    | ctrl-F         | zoom to fit notes           |
| Editor    | Q              | quantize                    |
| Editor    | G              | snap-to-grid                |
| Editor    | A              | auto-scroll during playback |
| Editor    | S              | solo the edited phrase      |
| Editor    | H              | hear the selected notes     |
| Editor    | ctrl-alt-space | play the edited phrase      |
