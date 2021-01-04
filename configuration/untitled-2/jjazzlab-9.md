# JJazzLab

Use the **Song Structure Editor** to:

* Define the order of sections, eg “AABA”, “verse verse chorus verse”, …
* Select the rhythm\(s\) to be used
* Adjust the rhythm parameters to introduce dynamics, eg variation, intensity, fill, muted instrument, …

## Song Parts <a id="song-parts"></a>

A song part is linked to a parent section of the chord leadsheet \(see the [Chord Leadsheet Editor](https://www.jjazzlab.com/en/doc/chord-leadsheet-editor)\).

A song part has a name, a rhythm and a value for each of the rhythm parameters.

To add a new song part:

* drag a section from the [Chord Leadsheet Editor](https://www.jjazzlab.com/en/doc/chord-leadsheet-editor) into the Song Structure Editor, or
* right-click menu Insert, or
* copy an existing song part: drag it while pressing the ctrl key, use copy & paste, or right-click menu Duplicate

By default the name of the song part is the name of the parent section. If the song part is renamed, the parent section is shown below the name between parenthesis.

If some contiguous song parts share the same name, then the name is displayed only on the first song part and a line is shown on the contiguous song parts. Clicking this line will select all the related song parts.

Song parts can be reordered by dragging them using the mouse.

## Editing <a id="editing"></a>

Song Parts can be edited directly from the Song Structure Editor or from the Song Part editor tab. Edited values will impact all the selected song parts or rhythm parameters.

The Song Part’s name, rhythm and rhythm parameters can be edited. When changing the rhythm, JJazzLab tries to adapt the values of the previous rhythm parameters to the new rhythm parameters.

## Mouse shortcuts <a id="mouse-shortcuts"></a>

| Selection | Mouse | Action |
| :--- | :--- | :--- |
| Song Part, Rhythm Parameter        | simple-click        | select |
| Song Part | double-click        | edit song part’s name |
| Name | click        | edit song part’s name |
| Rhythm | click        | change rhythm |
| Rhythm Parameter | double-click        | show the song part in the song part editor |
| Editor, Song Part, Rhythm Parameter        | right-click        | open the popup menu |
| Rhythm Parameter | mouse wheel | change value |
| Editor | ctrl mouse wheel        | change the X zoom factor |

## Keyboard shortcuts <a id="keyboard-shortcuts"></a>

_Tip_: many actions are also available via the context menu \(right-click on Windows/Linux, ctrl-click on Mac\), and when available the associated keyboard is displayed.

| Selection | key | Action |
| :--- | :--- | :--- |
| Song Part, Rhythm Parameter        | enter        | edit song part’s name |
| Song Part, Rhythm Parameter        | R        | change rhythm |
| Song Part, Rhythm Parameter        | I        | insert song part |
| Song Part, Rhythm Parameter        | ctrl-I        | insert song part at the end |
| Song Part, Rhythm Parameter        | D        | duplicate song part\(s\) |
| Song Part        | delete        | delete song part\(s\) |
| Rhythm Parameter        | ctrl-up/down        | next/previous rhythm parameter value |
| Rhythm Parameter        | Z        | reset rhythm parameter to default value |
| Song Part        | ctrl-C/X/V | copy/cut/paste song part\(s\) |
| editor        | ctrl-Z/Y        | undo/redo |
| editor        | ctrl-F        | zoom to fit width |

