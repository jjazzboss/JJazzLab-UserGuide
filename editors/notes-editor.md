# Notes editor

JJazzLab embeds a Midi notes editor, which can be used to edit user tracks or song part custom phrases (see the Custom phrase rhythm parameter).

<figure><img src="../.gitbook/assets/2023-12-31 23_11_42-JJazzLab  4.0.2.png" alt=""><figcaption><p>Melodic track</p></figcaption></figure>

<figure><img src="../.gitbook/assets/2024-01-01 00_06_53-JJazzLab  4.0.2.png" alt=""><figcaption><p>Drums tra</p></figcaption></figure>

## Zooming

You can use the main application zoom sliders in the lower right corner, or use **ctrl+mouse-wheel** for horizontal zoom, **ctrl+shift+mouse-wheel** for vertical zoom.&#x20;

Use **ctrl-F** to zoom to fit width.

<figure><img src="../.gitbook/assets/2023-12-31 23_37_35-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

## Snap to grid

Use the **Snap to grid** button to snap notes to the grid. The size of the grid can be set using the drop-down list:

<figure><img src="../.gitbook/assets/2023-12-31 23_20_16-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
When you move or resize notes with the **Select tool**, you can temporarily reverse the "snap to grid" setting by pressing **alt**.
{% endhint %}

## Edit tools

You can use 3 tools to modify notes: **select tool**, **draw tool**, **erase tool**.&#x20;

Tools can be selected using buttons from the notes editor top toolbar, or by right-clicking in the editor:

<figure><img src="../.gitbook/assets/2023-12-31 23_14_25-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

#### Select tool

Use the select tool to select, move, resize, copy, delete notes. Drag to select several notes.

<figure><img src="../.gitbook/assets/2023-12-31 23_25_52-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

#### Changing notes velocity

First select the notes to change. Then either use the velocity spinner in the toolbar, or use **alt + mouse-wheel** or **alt + page up/down**.

<figure><img src="../.gitbook/assets/2023-12-31 23_29_11-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

#### Importing notes

You can import notes by dragging an external Midi file into the editor. You can also drag from an individual track in the mix console.

<figure><img src="../.gitbook/assets/2023-12-31 22_54_43-JJazzLab  4.0.2.png" alt=""><figcaption><p>Importing a Midi file in the editor</p></figcaption></figure>

{% hint style="warning" %}
If the imported Midi file contains notes from several Midi channels, then JazzLab **only imports the notes which match the edited Midi channel.**&#x20;

If the imported Midi file only contains notes from a single channel, then JJazzLab imports the notes with the channel set the edited Midi channel.
{% endhint %}
