# Notes editor

JJazzLab embeds a Midi notes editor which is used to [**edit user tracks**](notes-editor.md#edit-a-user-track) or [**song part custom phrases**](notes-editor.md#edit-a-custom-phrase-for-a-song-part)**.**

<figure><img src="../.gitbook/assets/2024-12-30 11_01_51-JJazzLab  4.1.2.png" alt=""><figcaption><p>Melodic track</p></figcaption></figure>

<figure><img src="../.gitbook/assets/2024-01-01 00_06_53-JJazzLab  4.0.2.png" alt=""><figcaption><p>Drums track</p></figcaption></figure>

{% hint style="warning" %}
The score panel shows a **simplified musical notation:** it is not editable and notes are just placed at the right position without any other adjustment (no beams, etc.).&#x20;
{% endhint %}

## Opening the notes editor

### Edit a user track

The notes editor is automatically opened when you [add a user track](mix-console.md#adding-user-tracks). For existing user tracks, click the edit button in the track overview component, as shown below.&#x20;

<figure><img src="../.gitbook/assets/2023-12-31 22_02_16-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

Rhythm tracks can also be edited with the notes editor by cloning them first as a user track :

<figure><img src="../.gitbook/assets/2023-12-31 21_58_28-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

### Edit a Custom phrase for a song part

In the song structure editor, click the top-left button of a Custom phrase rhythm parameter:

<figure><img src="../.gitbook/assets/2024-01-05 12_40_44-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

Then select the phrases you wish to customize and press Edit to open the notes editor.

<figure><img src="../.gitbook/assets/2024-01-05 11_52_05-Customize phrases for song part _A_ - bars 1..8 (1).png" alt=""><figcaption></figcaption></figure>

## Moving and zooming

You can move the editor by pressing **ctrl + dragging** in the top ruler as shown below:

<figure><img src="../.gitbook/assets/2024-01-01 00_12_51-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

You can use the main application zoom sliders in the lower right corner, or use **ctrl+mouse-wheel** for horizontal zoom, **ctrl+shift+mouse-wheel** for vertical zoom.&#x20;

Use **ctrl-F** to zoom to fit width.

<figure><img src="../.gitbook/assets/2023-12-31 23_37_35-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

## Playback of the edited phrase

Use the toolbar button, or press **ctrl-shift-SPACE,** to start the playback in loop mode of the edited phrase, or of the **playback loop zone** if it is set.

<figure><img src="../.gitbook/assets/2024-05-16 22_49_35-JJazzLab  4.0.3-SNAPSHOT.png" alt=""><figcaption><p>Start playback button</p></figcaption></figure>

### Playback loop zone

A playback loop zone can be set by **mouse dragging** in the top **ruler**. Use **shift+click** in the ruler to extend the loop zone. **Click** in the ruler to remove the loop zone.

<figure><img src="../.gitbook/assets/2024-05-16 22_47_02-JJazzLab  4.0.3-SNAPSHOT.png" alt=""><figcaption></figcaption></figure>

## Snap to grid

Use the **Snap to grid** button (or press **G**) to snap notes to the grid when you draw/move/resize them. The size of the grid can be set using the drop-down list (1/4=quarter note, 1/8=quaver, ...):

<figure><img src="../.gitbook/assets/2023-12-31 23_20_16-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
When you move or resize notes with the **Select tool**, you can temporarily reverse the "snap to grid" setting by pressing **alt**.
{% endhint %}

To change the position of existing notes, use [Quantize](notes-editor.md#quantize-notes).

## Edit tools

You can use 3 tools to modify notes: **select tool**, **draw tool**, **erase tool**. The 2 first edit tools are sensitive to the [snap to grid](notes-editor.md#snap-to-grid) settings.

Tools can be selected using buttons from the notes editor top toolbar, or by right-clicking in the editor:

<figure><img src="../.gitbook/assets/2023-12-31 23_14_25-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

Use the **select tool** to select, move, resize, copy (ctrl-C), delete notes (press delete). **Drag** to select several notes. Use **ctrl-drag** notes to duplicate notes. **ctrl-shift-I** invert the notes selection.

<figure><img src="../.gitbook/assets/2023-12-31 23_25_52-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
If one or more notes are selected, pasted notes are aligned with the first selected note. If no notes selected, pasted notes are aligned to the left side of the notes editor.
{% endhint %}

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

You can also **humanize** all or selected notes. Humanization introduces slight random variations in the notes start position and velocity.&#x20;

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

<table data-header-hidden><thead><tr><th width="253.33333333333331">Selection</th><th>Mouse</th><th>Action</th></tr></thead><tbody><tr><td>Notes</td><td>ctrl-click </td><td>select multiple notes</td></tr><tr><td>Editor</td><td>drag</td><td>select multiple notes</td></tr><tr><td>Notes</td><td>drag</td><td>move/resize</td></tr><tr><td>Notes</td><td>ctrl-drag</td><td>duplicate notes</td></tr><tr><td>Notes</td><td>alt-drag</td><td>move/resize with snap-to-grid setting reversed</td></tr><tr><td>Notes</td><td>alt-wheel</td><td>change velocity</td></tr><tr><td>Editor</td><td>wheel</td><td>move editor up down</td></tr><tr><td>Editor</td><td>shift-wheel</td><td>movbe editor left right</td></tr><tr><td>Editor</td><td>ctrl-wheel</td><td>zoom horizontally</td></tr><tr><td>Editor</td><td>ctrl-shift-wheel</td><td>zoom vertically</td></tr><tr><td>Editor</td><td>ctrl-drag</td><td>Move editor</td></tr><tr><td>Ruler</td><td>drag</td><td>set playback loop zone</td></tr><tr><td>Ruler</td><td>shift-click</td><td>extend playback loop zone</td></tr><tr><td>Ruler</td><td>click</td><td>remove playback loop zone</td></tr></tbody></table>

## Keyboard shortcuts

| Selection | Key            | Action                      |
| --------- | -------------- | --------------------------- |
| Notes     | alt-up/down    | change velocity             |
| Notes     | ctrl-C/X/V     | copy/cut/paste notes        |
| Notes     | delete         | delete notes                |
| Notes     | ctrl-shift-I   | invert notes selection      |
| Editor    | ctrl-F         | zoom to fit notes           |
| Editor    | Q              | quantize                    |
| Editor    | G              | snap-to-grid                |
| Editor    | A              | auto-scroll during playback |
| Editor    | S              | solo the edited phrase      |
| Editor    | H              | hear the selected notes     |
| Editor    | Home/End       | Move editor to start/end    |
| Editor    | ctrl-alt-space | play the edited phrase      |
| Editor    | ctrl-Z/Y       | undo/redo                   |
