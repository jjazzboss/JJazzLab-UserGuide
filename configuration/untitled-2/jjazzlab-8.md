# JJazzLab

Use the **chord leadsheet editor** to:

* Add chord symbols, eg _Cm6_, _Ab7_
* Add sections, eg _A_, _B_, _verse_, _chorus_, …
* Move and edit chords to adjust rhythm accents, interpretation or harmony

## Chord symbols <a id="chord-symbols"></a>

### Input <a id="input"></a>

Select a bar or a chord symbol then:

* type the first letter of the chord symbol \(‘A’ to ‘G’\), or
* press ENTER, or
* double-click, or
* right-click menu, Edit

You can also select an existing chord symbol and move it while pressing the ctrl button, it will create a new copy that can be edited.

To move a chord symbol just select it and move it with the mouse.

To input a complete leadsheet the easier way is to select the first bar, directly type in the chord symbols, press ENTER \(it will automatically select the next bar\), type in the chord symbols for the second bar, etc.

To change the size of the leadsheet, select a bar then right-click menu and select Set End Bar.

Use ctrl-click or shift-click for multiple selection.

### Aliases <a id="aliases"></a>

JJazzLab recognizes many aliases for each chord symbol. For example _C7M_ can be written _Cmaj7_, _Cma7_, _CM7_, _CMAJ7_ etc.

You can add more aliases using the Chord Symbols panel in the Options/Preferences.

### Interpretation <a id="interpretation"></a>

Select a chord symbol, edit it and select the Interpretation tab.

The Interpretation tab lets you decide how this chord symbol should be played:

* **Normal**
* **Accent**: add a rhytmic accent and randomly a crash cymbal. You can make the accent stronger, or make sure a crash cymbal is played or not played.
* **Hold**: add a rhythmic accent and hold notes until next chord symbol. If extended more instruments are hold.
* **Shot**: add a rhythmic accent with chord notes played briefly. If extended more instruments are shot.
* **Pedal bass**: bass line will only play the bass note \(for ex. F for _Fm7_ or C for _Fm7/C_\). This setting is on by default when you enter a slash chord.

_Note: each rhythm generation engine may render these Interpretation parameters differently_

  
 The shape of the marker below the chord symbol depends on the interpretation mode:

  
 For example, in order to render: 

you could use the following interpretation parameters:  _Hint: see below the keyboard shortcuts to easily change the interpretation of selected chords._

### Harmony <a id="harmony"></a>

Select a chord symbol, edit it and select the Harmony tab.

The Harmony tab lets you select the scale to be used when rendering the music for this chord symbol.

_Example: Suppose that the reference bass line for Eb7M contains a Ab \(4th degree of the Eb major scale\). If you select the lydian mode \(which has a sharp 11th degree\) then the reference bass note Ab will be rendered as A for this chord symbol._

By default no scale is selected: each rhythm generation engine will decide the “best” scale to use.

### Alternate chord symbol <a id="alternate-chord-symbol"></a>

Select a chord symbol, edit it and select the Alternate chord symbol tab.

This tab lets you define an alternate chord symbol which will be used when some conditions are met. The alternate chord symbol can be a completly different chord symbol, the same but with a different interpretation or harmony, or no chord symbol at all \(void chord\). This is useful when you need to introduce a slight variation during a song.

Chord symbols which have an alternate chord symbol defined are displayed with a different color \(see image below\).

_Example:_

In the Carlos Santana’s “Europa” song, the 1st ending of the theme is a _Cm7_, but the 2nd one is a C major. To implement this in JJazzLab, one solution could be to duplicate section A1 to create section A2 with the different ending, then update the song structure accordingly. This is perfectly fine, but when changes are minor the alternate chord symbol can provide a simpler solution.

You can see below \(and in the dialog snapshot above\) that a _C7M_ alternate chord has been created for _Cm7_. _C7M_ will be used for all song parts \(see the [Song Structure Editor](https://www.jjazzlab.com/en/doc/song-structure-editor)\) where the marker is set to Theme2. On the image below it means the _C7M_ will be used on the 2nd occurence of section A1.

There is another alternate chord symbol example in the 3rd bar: _A7_. If you listen to the original song you’ll notice that they play a _A7_ on the last beat of the 3rd bar only during solos. So the _A7_ chord symbol defines its alternate chord symbol as the “void chord symbol” \(same as no chord symbol\) when marker is _not_ “Solo”.

## Sections input <a id="sections-input"></a>

Typical sections are ‘intro’, ‘verse’, ‘chorus’, etc.

A Song section is the basic unit used by JJazzLab to define the song structure \(see the [Song Structure Editor](https://www.jjazzlab.com/en/doc/song-structure-editor)\). There is always a section defined on the first bar.

To add a section select a bar which is not after the end then:

* press ENTER, or
* double-click, or
* right-click menu, Edit

The new section name must be different than the existing one.

### Force a section at new line <a id="force-a-section-at-new-line"></a>

You can force a section which is not on the first bar of a row to start on the next line. This can be useful when some sections have an odd number of bars.

Select a bar with a section defined or select the section itself, right-click menu “Force Section at New Line”.

  
 This will result in the display below. 

## Mouse shortcuts <a id="mouse-shortcuts"></a>

| Selection | Mouse | Action |
| :--- | :--- | :--- |
| Bar, Chord Symbol, Section        | simple-click        | select |
| Chord Symbol        | double-click        | edit using the chord symbol editor dialog |
| Bar, Section        | double -click        | edit using the bar editor dialog |
| Bar, Chord Symbol, Section        | right-click        | open the popup menu |
| Chord Symbol | mouse wheel | transpose chord symbol |
| Chord Symbol | shift mouse wheel        | change chord type |
| Editor | ctrl mouse wheel | change the X zoom factor |

## Keyboard shortcuts <a id="keyboard-shortcuts"></a>

_Tip_: many actions are also available via the context menu \(right-click on Windows/Linux, ctrl-click on Mac\), and when available the associated keyboard is displayed.

| Selection | key | Action |
| :--- | :--- | :--- |
| Chord Symbol        | enter        | edit using the chord symbol editor dialog |
| Bar, Section        | enter        | edit using the bar editor dialog |
| Bar        | ctrl-E        | set end bar |
| Bar        | I        | insert bars |
| Bar        | delete        | clear bar contents |
| Chord Symbol, Section        | delete        | remove |
| Bar        | shift-delete        | remove |
| Chord Symbol | ctrl-up/down | transpose |
| Chord Symbol | P | change interpretation |
| Chord Symbol | S | stronger accent |
| Chord Symbol | H | crash cymbal/no crash |
| Chord Symbol | X | hold/shot extended |
| Chord Symbol, Section | ctrl-A | select similar items from the current section. Then from the chord leadsheet. |
| Bar, Chord Symbol, Section        | ctrl-C/X/V | copy/cut/paste items |
| Editor        | ctrl-Z/Y        | undo/redo |
| Editor        | ctrl-O        | set current song active \(On/Off\) |
| Editor        | ctrl-W        | close current song |

