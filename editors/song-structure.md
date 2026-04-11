# Song structure

Use the **song structure editor** to:

* Define the order of sections as **song parts**, eg "AABA" or "verse verse chorus verse"
* Select which **rhythms** (music styles) to use and when
* Adjust the **rhythm parameters** of song parts to introduce dynamics, eg variation, intensity, drums fill, muted instrument, ...

![](../.gitbook/assets/FullSongStructureEditorText.png)

## Song parts

A **song part** is linked to a parent **section** of the [chord lead sheet](chord-lead-sheet.md).

<figure><img src="../.gitbook/assets/SectionAndSongParts.png" alt=""><figcaption></figcaption></figure>

**Song parts let you define in which order sections are played, and how**.&#x20;

A song part has a name, a **rhythm** and a value for each of the [**rhythm parameters**](song-structure.md#rhythm-parameters). Rhythm parameters let you change how the rhythm is played for this song part.

In the image above, song parts define the following section order: **Intro, A, A, B, A**. All song parts use the same rhythm(MediumJazz.S737.sst). Note that the 3rd and last song parts will use a different rhythm variation (Main B-1) with a drums break on the last bar.

By default the name of the song part is the name of the parent section. If the song part is renamed, the parent section is shown below the name in brackets (see 2nd and 3rd song parts above).

{% hint style="info" %}
If some contiguous song parts share the same name, then the name is displayed _only on the first song part and a line is shown_ on the contiguous song parts (see image below).

Clicking this line will select all the related song parts.
{% endhint %}

![](../.gitbook/assets/songparts-samename.png)

## Editing

To add a new song part:

* **drag a section** from the chord lead sheet into the song structure editor, or
* right-click menu **Insert**, or
* copy an existing song part: drag it while pressing the ctrl key, use copy & paste, or right-click menu **Duplicate**

Song parts can be reordered by **dragging them using the mouse** (use ctrl+mouse drag to duplicatea song part). Copy/cut/paste commands work as well both on song parts and rhythm parameters.

Edition of song part **name**, **rhythm** and **parameters** can be done directly from the song structure editor using the [mouse](song-structure.md#mouse-shortcuts) or [keyboard shortcuts](song-structure.md#keyboard-shortcuts), or via the [song part editor](song-structure.md#song-part-editor).

{% hint style="success" %}
To edit several song parts or rhythm parameters in one shot:

* select multiple items with **ctrl+click** or **shift-click**
* Do the edit (for example change the rhythm, or increase intensity)

Change is applied to all selected items.
{% endhint %}

Use the popup menu (**right-click** on windows/Linux, **ctrl-click** on Mac) to see commands available for the current selection (song part or rhythm parameter), as shown in the 2 images below.

![Song part popup menu](../.gitbook/assets/SongPartPopupMeny.png)

![Rhythm parameter popup menu](../.gitbook/assets/RhythmParameterPopupMenu.png)

For most of the rhythm parameters, **the easiest way** to edit the value is to **select it** and use the **mouse-wheel**.

Some rhythm parameters have a custom edit dialog, which can be called as shown below.

<figure><img src="../.gitbook/assets/2024-01-05 11_27_00-JJazzLab  4.0.2.png" alt=""><figcaption><p>A rhythm parameter with a custom editor</p></figcaption></figure>

{% hint style="success" %}
Copy & paste can be used to easily **duplicate rhythm parameter values**.

Suppose you want to apply the drums transform value from one song part (e.g. ">Open hi-hat" in image above) to other song parts:

* In the song structure editor, select the original rhythm parameter and Copy (ctrl-C)
* Select the same rhythm parameter in other song parts (use ctrl-click or shift-click for multiple selection) then Paste (ctrl-V)
{% endhint %}

When selecting several contiguous rhythm parameters, you can use the **Adjust values** submenu in the rhythm parameter popup menu to interpolate values between the first and the last selected values. In the example below, we used it to gradually increase the tempo from 100% to 108%.

![](../.gitbook/assets/AdjustRpValues.png)

## Song part editor

Song part editor provides an additional way to edit the selected song part(s).

Use the song part editor to edit rhythm parameters which need user to select (ctrl-click) one or more values from a list, such as the Mute parameter.

<figure><img src="../.gitbook/assets/2024-01-05 11_37_05-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

## Change rhythm (music style)

Each song part can have its own rhythm.

{% hint style="warning" %}
Midi can only accommodate 16 channels (1 channel per instrument), and many rhythms use 7 or 8 instruments. So in order to have a song with more than 2 rhythms, you need to pick rhythms with few instruments.
{% endhint %}

When a song part is created, JJazzLab selects the last rhythm used in the song for this time signature, or it selects the **default rhythm** for this time signature.

{% hint style="info" %}
You can define the **default rhythm** for each time signature in the **Rhythms** tab of the **Options/Preferences**.
{% endhint %}

To change the rhythm, select a song part and press **R,** or click the rhythm name to open the **rhythm selection dialog**.

![](../.gitbook/assets/RhythmSelectionDialog.png)

When changing the rhythm, JJazzLab tries to adapt the values of the previous rhythm parameters to the new rhythm parameters.

If you want to remove a rhythm change in the middle of a song, select the song part and use **Remove Rhythm Change** from the song part popup menu.

![](../.gitbook/assets/RemoveRhythmChange.png)

## Rhythm parameters

**Rhythm parameters** let you adjust how a rhythm (music style) is played for a given song part.

{% hint style="success" %}
Rhythm parameters are a simple & powerful tool to **introduce variations in a backing track**, which make it more fun to play with.
{% endhint %}

In the image below, you can see two **song parts** using the same [jjSwing ](../rhythm-engines/jjswing-rhythm-engine.md)rhythm but with very different **rhythm parameters** -as a result, they will sound quite different.&#x20;

This example is a bit extreme; usually, adjusting just a few parameters is enough to avoid a boring backing track. Note that you can hide the rhythm parameters you don't use by adjusting the the [compact view](song-structure.md#compact-full-view) settings.

<figure><img src="../.gitbook/assets/ManyRhythmParameters.png" alt=""><figcaption></figcaption></figure>

The most common rhythm parameters are described below.&#x20;

{% hint style="info" %}
Note that a [rhythm engine](/broken/pages/-MQSAs6SfPTmre5f3rhY) can define its own custom rhythm parameters. For example [jjSwing ](../rhythm-engines/jjswing-rhythm-engine.md)defines [Bass style](../rhythm-engines/jjswing-rhythm-engine.md#bass-style) and [Drums style](../rhythm-engines/jjswing-rhythm-engine.md#drums-style).
{% endhint %}

### Variation

A rhythm parameter to indicate which rhythm (style) variation must be used. The [YamJJazz engine](../rhythm-engines/yamjjazz-rhythm-engine/) rhythms usually have 4 _Main_ variations, plus some _Intros_, _Endings_, and _Fills_.

### Intensity

This parameter defines the intensity of the generated backing track.

A rhythm engine might simply increase/decrease the Midi velocity of the backing track notes depending on this parameter, but it could also generate more/less notes, etc.

### Drums Fill

This parameter defines when a **drums fill** (or **break**) should be played at the end of the song part (_**never**_, _**always**_, _**randomly**_, ...).

The special _**fade\_out**_ value does not produce a drums fill, instead it gradually decreases the notes velocity until the end of the song part.

### Mute

This parameter is used to **mute one of more instruments** during this song part. To edit this parameter it's easier to use the [song part editor](song-structure.md#song-part-editor)**.**

### Marker

This parameter is useful only if you use substitute chord symbols, as explained [here](chord-lead-sheet.md#substitute-chord-symbol).

### Tempo factor

Use this parameter to slow down or accelerate the tempo of the song part as a percentage (50% to 200%) of the song's tempo. The number in brackets is the resulting tempo.

<figure><img src="../.gitbook/assets/TempoFactor.png" alt=""><figcaption><p>Tempo factor example with song's tempo=142</p></figcaption></figure>

### Drums transform

This parameter lets you change some drums notes for the song part.

This is an **easy way to alter the drums track** to introduce some variations in your song.

For example you can make the hi-hat louder, transform the closed hi-hat into ride cymbal, or just add percussions!

![](../.gitbook/assets/DrumsTransform.png)

### Custom phrase

This parameter lets you customize one or more rhythm phrases for a song part.\
\
**Example**: you want to change the rhythm bass phrase at the end of the second verse\
\
Edit the Custom phrase rhythm parameter of the corresponding song part, then edit the Bass track. The default bass phrase will appear in the [notes editor](notes-editor.md) and you'll be able to change it.\
\
If you want this customized bass phrase to also be used in the last verse of the song, just [copy the rhythm parameter value](song-structure.md#editing) and paste it in the last song part.

![](<../.gitbook/assets/2024-01-05 11_52_05-Customize phrases for song part _A_ - bars 1..8 (1).png>)

### Track overrides

This parameter lets you use one or more tracks from other rhythms.

_Example: your song uses a 8-beat pop rhythm. You want to spice up the chorus song part and use **Track overrides** to replace the 8-beat original bass line by the bass line from a bossa-nova rhythm._

<figure><img src="../.gitbook/assets/TrackOverride.png" alt=""><figcaption></figcaption></figure>

Other usage examples:

* You like a jazz Yamaha style except the bass line which does not sound good. Use the Track overrides parameter to replace the bass line by [jjSwing](../rhythm-engines/jjswing-rhythm-engine.md)'s realistic walking bass.
* The override rhythm can be the same than the original rhythm. For example this lets you override the piano part by the bass part from the same rhythm, so that the bass line is doubled piano+bass on a given song part.

### Compact / full view

By default only a subset of the rhythm parameters are visible, this is the **compact view**.

Click on the button below or press 'V' to switch between compact and full view.

![](../.gitbook/assets/CompactView.png)

The **compact view settings** button, just above the compact view button, lets you choose which rhythm parameters are visible in the compact view. These settings are saved with the song.

<figure><img src="../.gitbook/assets/2024-01-05 22_43_31-Compact view settings.png" alt=""><figcaption><p>Compact view settings</p></figcaption></figure>

As a shortcut, you can directly hide a rhythm parameter (i.e. make it non visible in the compact view) by clicking on the X button in the upper left corner, as shown below.

<figure><img src="../.gitbook/assets/QuickHideRp.png" alt=""><figcaption></figcaption></figure>

## Mouse shortcuts

<table data-header-hidden><thead><tr><th width="253.33333333333331">Selection</th><th>Mouse</th><th>Action</th></tr></thead><tbody><tr><td>Selection</td><td>Mouse</td><td>Action</td></tr><tr><td>song part, rhythm param.</td><td>click</td><td>select</td></tr><tr><td>song part</td><td>double click</td><td>edit song part name</td></tr><tr><td>song part name</td><td>click</td><td>edit</td></tr><tr><td>rhythm</td><td>click</td><td>select a rhythm</td></tr><tr><td>editor, song part, rhythm param.</td><td>right-click</td><td>open popup menu</td></tr><tr><td>rhythm parameter</td><td>double-click</td><td>edit value</td></tr><tr><td>rhythm parameter</td><td>mouse wheel</td><td>change value</td></tr><tr><td>editor</td><td>shift mouse wheel</td><td>scroll horizontally</td></tr><tr><td>editor</td><td>alt mouse wheel</td><td>scroll vertically</td></tr><tr><td>editor</td><td>ctrl mouse wheel</td><td>zoom horizontally</td></tr><tr><td>editor</td><td>ctrl-shift mouse wheel</td><td>zoom vertically</td></tr></tbody></table>

## Keyboard shortcuts

{% hint style="info" %}
Many actions are also available via the context menu (right-click on Windows/Linux, ctrl-click on Mac), and when available the associated shortcut is displayed.
{% endhint %}

| Selection                | Key          | Action                 |
| ------------------------ | ------------ | ---------------------- |
| song part, rhythm param. | enter        | edit song part name    |
| song part, rhythm param. | R            | select rhythm          |
| song part, rhythm param. | I            | insert song part       |
| song part, rhythm param. | ctrl-I       | append song part       |
| song part, rhythm param. | D            | duplicate song part(s) |
| song part                | delete       | delete song part(s)    |
| rhythm parameter         | ctrl-up/down | next/previous value    |
| rhythm parameter         | Z            | reset param. value     |
| song part                | ctrl-C/X/V   | copy/cut/paste         |
| editor                   | ctrl-Z/Y     | undo/redo              |
| editor                   | ctrl-F       | zoom to fit width      |
| editor                   | V            | compact or full view   |
