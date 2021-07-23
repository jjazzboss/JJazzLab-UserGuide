---
title: Song Structure Editor
date: '2017-10-17T15:26:15.000Z'
draft: false
weight: 320
helpTitle: false
---

# ソング構成

Use the **song structure editor** to:

* Define the order of sections, eg "AABA", "verse verse chorus verse", ...
* Select the **rhythm**\(s\) to be used 
* Adjust the **rhythm parameters** to introduce dynamics, eg variation, intensity, fill, muted instrument, ...

![](../../.gitbook/assets/songstructureeditor.png)

## Song parts

A **song part** is linked to a parent **section** of the [chord lead sheet](chord-lead-sheet.md).

A song part has a name, a **rhythm** and a value for each of the **rhythm parameters**.

To add a new song part:

* drag a section from the chord lead sheet into the song structure editor, or
* right-click menu **Insert**, or 
* copy an existing song part: drag it while pressing the ctrl key, use copy & paste, or right-click menu **Duplicate**

By default the name of the song part is the name of the parent section. If the song part is renamed, the parent section is shown below the name.

If some contiguous song parts share the same name, then the name is displayed only on the first song part and a line is shown on the contiguous song parts. Clicking this line will select all the related song parts.

![](../../.gitbook/assets/songparts-samename.png)

Song parts can be reordered by dragging them using the mouse.

## Editing

You can modify the song part **name**, **rhythm**, and **rhythm parameter** values.

Edition is done directly from in the song structure editor using the [mouse](song-structure.md#mouse-shortcuts), or from the **song part editor** \(see snapshot at the top of this page\). Edited values will impact all the selected song parts or rhythm parameters.

Press **R** or click the rhythm name to open the **rhythm selection dialog**.

![](../../.gitbook/assets/rhythm-selection-dialog.png)

When changing the rhythm, JJazzLab tries to adapt the values of the previous rhythm parameters to the new rhythm parameters.

{% hint style="warning" %}
Midi can only accommodate 16 channels, and many rhythms use 7 or 8 instruments. That's why it's difficult in practical to have a song with more than 2 rhythms.
{% endhint %}

## マウスショートカット

| 対象 | マウス | 動作 |
| :--- | :--- | :--- |
| song part, rhythm param. | click | select |
| song part | double click | edit song part name |
| song part name | click | edit  |
| rhythm | click | select a rhythm |
| editor, song part, rhythm param. | right-click | open popup menu |
| rhythm parameter | double-click | edit value |
| rhythm parameter | mouse wheel | change value |
| rhythm parameters | shift+mouse wheel | make values identical then change value |
| editor | ctrl mouse wheel | change X zoom factor |

## キーボードショートカット

{% hint style="info" %}
Many actions are also available via the context menu \(right-click on Windows/Linux, ctrl-click on Mac\), and when available the associated shortcut is displayed.
{% endhint %}

| 対象 | キー | 動作 |
| :--- | :--- | :--- |
| song part, rhythm param. | enter | edit song part name |
| song part, rhythm param. | R | select rhythm |
| song part, rhythm param. | I | insert song part |
| song part, rhythm param. | ctrl-I | append song part |
| song part, rhythm param. | D | duplicate song part\(s\) |
| song part | delete | delete song part\(s\) |
| rhythm parameter | ctrl-up/down | next/previous value |
| rhythm parameter | Z | reset param. value |
| song part | ctrl-C/X/V | copy/cut/paste |
| editor | ctrl-Z/Y | undo/redo |
| editor | ctrl-F | zoom to fit width |

