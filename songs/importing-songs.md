# Importing songs

## Band In A Box song files

JJazzLab can import .SG\* or .MG\* song files.

Only the following Band-In-A-Box data are used to generate the corresponding JJazzLab song :

* **song structure**: chorus start, chorus end, number of chorus, tag after, tag start, tag end, 2 bar ending
* **chord symbols**: name, position (including optional push settings), rest/hold/shot settings
* **song settings**: allow push/rest in first/middle/last chorus.

The song import feature is not 100% reliable, but most of the files should be OK.

{% hint style="danger" %}
**By default imported songs will be in 4/4**. If you know that the imported song is in 3/4, then when import is done just select the initial time signature and use righ-click menu **Set time signature** to fix the time signature.
{% endhint %}

## musicXML files

JJazzLab can import musicXML (.xml) or compressed musicXML (.mxl).&#x20;

The import is limited to the time signatures and chord symbols.

## .CSV files

JJazzLab can read chords from .csv files.&#x20;

There are 2 possible formats to specify a chord symbol, TIME-BASED or BEAT-BASED.

**TIME-BASED: "pos\_in\_seconds, chord\_symbol"**\
The time signature and tempo must be set first so that pos\_in\_seconds can be converted into bar/beat. If not set, the default values are 4/4 and 120bpm.

Example:\
`timeSignature=3/4`\
`tempoBPM=60`\
`0, C`\
`3, F7`\
`4.5, Eb7`\
`6, D7`

**BEAT-BASED : "bar, beat, chord-symbol"**

bar and beat are 0-based by default.

Example:\
`0, 0, C`\
`1, 0, F7`\
`1, 1.5, Eb7`\
`2, 0, D7`\


OTHER FORMAT INFORMATION

* Use // to add comments
* "title=My song name" : if specified the created song will use this title as name
* "useBase1" : if specified the bar/beat positions start at 1
* Accepted delimiter characters are , ; or space or tab

## Impro-Visor leadsheet files

JJazzLab can import Impro-Visor (.ls) leadsheet files.&#x20;

The import is limited to the time signatures and chord symbols.

