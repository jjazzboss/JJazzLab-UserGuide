---
description: >-
  JJazzLab can import songs from different file types using the menu File/Import
  songs.
---

# Importing songs

## Band In A Box song files (.SGU etc.)

JJazzLab can import .SG\* or .MG\* song files.

Only the following Band-In-A-Box data are used to generate the corresponding JJazzLab song :

* **song structure**: chorus start, chorus end, number of chorus, tag after, tag start, tag end, 2 bar ending
* **chord symbols**: name, position (including optional push settings), rest/hold/shot settings
* **song settings**: allow push/rest in first/middle/last chorus.

The song import feature is not 100% reliable, but most of the files should be OK.

{% hint style="danger" %}
**By default imported songs will be in 4/4**. If you know that the imported song is in 3/4, then when import is done just select the initial time signature and use righ-click menu **Set time signature** to fix the time signature.
{% endhint %}

## musicXML files (.xml, .mxl, musicxml)

JJazzLab can import musicXML (.xml, .musicxml) or compressed musicXML (.mxl). It has been tested successfully with musicXML files exported from iRealPro.&#x20;

What is imported: &#x20;

* Chord symbols
* Time signatures
* Section titles such "INTRO", "A", "B" found in **direction/direction-type/rehearsal** elements.
* Repeats, endings (1. 2. 3...), tocoda, coda, segno, DC al coda, DC al fine, DS al coda, DS al fine, as found in **sound** and **barline** elements.
* Music style information found in the **groove** type of a **play/other-play element.**



## Text files (.txt)

JJazzLab can read chords from text files. 3 formats are supported, GRID-BASED, TIME-BASED, BEAT-BASED.

#### **GRID-BASED: e.g. "| 3/4 Bb7M | D7#5  | Eb7M | Db7#11 |"**

`!` can be used instead of `|`.  `%` repeats the previous bar. Any bar can start with a time signature.

Example:

`|3/4 Bb7M | D7#5  | Eb7M  | Db7#11 |`\
`| Cm7     | G7     | C7M   |       |`\
`|4/4 Fm7  | Gm7 C7 | %     |  F7M  |`

{% hint style="success" %}
JJazzLab can directly import text files exported from ChordPulse (it ignores the `.` and `/` chars between chords).
{% endhint %}

#### **TIME-BASED: "pos\_in\_seconds, chord\_symbol"**

The time signature and tempo must be set first so that pos\_in\_seconds can be converted into bar/beat. If not set, the default values are 4/4 and 120bpm.

Example:\
`timeSignature=3/4`\
`tempoBPM=60`\
`0, C`\
`3, F7`\
`4.5, Eb7`\
`6, D7`

#### **BEAT-BASED : "bar, beat, chord-symbol"**

Note that by default bar and beat are expected to be 0-based (first bar of the song is bar 0). You can change that by adding "`useBase1`" at the beginning of the file, then bar and beat are expected to be 1-based.

Example:\
`0, 0, C`\
`1, 0, F7`\
`1, 1.5, Eb7`\
`2, 0, D7`

#### **Other text format information**

* Lines starting with `//` are ignored (comments)
* "`title=My song name`" : if specified the created song will use this title as name
* Accepted delimiter characters are `,` `;` or space or tab (time or beat-based format)



## Impro-Visor leadsheet files (.ls)

JJazzLab can import Impro-Visor (.ls) leadsheet files.&#x20;

The import is limited to the time signatures and chord symbols.

