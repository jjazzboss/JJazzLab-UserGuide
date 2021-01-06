# Output synth editor

{% hint style="info" %}
If you use the [JJazzLab SoundFont](jjazzlab-1.md) you may skip this page because you’ll only use one of the Output Synth presets. 

Read on if you need JJazzLab to control a specific synth, like a hardware synthesizer, VSTs, your own SoundFont, etc.
{% endhint %}

## Output Synth concept <a id="output-synth-concept"></a>

The Output Synth represents the Midi synth you have connected to the output of JJazzLab:

![](../.gitbook/assets/outputsynth-concept%20%281%29.png)

 The Output Synth provides information used by JJazzLab for 3 important tasks:

1. Propose the most relevant instruments for a given rhythm
2. Automatically remap drum sounds when needed \(there are several standard drum key maps, like the [GM drum key map](https://en.wikipedia.org/wiki/File:GMStandardDrumMap.gif)\)
3. Access the available instruments from the mix console

The Output Synth information can be edited in the Output Synth Editor. The information can be load/saved in configuration files. By default JJazzLab uses Default.cfg.

### Example <a id="example"></a>

You have connected your old GM-compatible Roland synthesizer to JJazzLab. So in the Output Synth editor you have checked “GM compatible”.

Your song uses the rhythm SimpleFolk.sty, a Yamaha style which defines 3 instruments:

* Bass, preferred instrument is GM ‘Acoustic Bass’
* Guitar, preferred instrument is XG ‘12 String Guitar’
* Drums, preferred drum kit is ‘Brush’ type with the XG drums key map

Using the Output Synth information \(“my synth is only GM compatible”\), JJazzLab will do the following before playing the song:

* Send a Midi message “Switch GM mode ON” to the Roland synth
* Bass: select the GM ‘Acoustic Bass’ via standard GM messages
* Guitar: select the GM ‘Steel Guitar’, which is the closest instrument from the XG ‘12 String Guitar’
* Drum: select the GM standard drums \(GM only has a single drum kit\), and remap all XG-specific drum notes to GM drum notes

In conclusion, JJazzLab uses the Output Synth information to make the rhythm sound as close as possible as the original rhythm \(as programmed by the rhythm designer\).

If your sound device/Midi synth corresponds to one of the configutations below, just apply the corresponding preset.

* **GM**: a GM-compatible synth
* **JJazzLab SoundFont**: a soundfont player with the JazzLab SoundFont loaded
* **Yamaha Tyros**: a Yamaha arranger keyboard of the Tyros/PSR family

## Default instruments <a id="default-instruments"></a>

The Ouput Synth Editor lets you map standard GM Instruments to Default Instruments of your choice. You can also set a default instrument for a ‘family’, e.g. all the organs.

  
 EXAMPLE: You mapped the GM instrument ‘Bright Piano’ to the JJazzLab SoundFont instrument ‘Hard FM EP’. Now each time a rhythm needs a GM Bright Piano, JJazzLab will use the ‘Hard FM EP’ instrument instead.

## Midi synth definition files \(Cakewalk .ins format\) <a id="midi-synth-definition-files-cakewalk-ins-format"></a>

JJazzLab can read Cakewalk instrument definition files \(.ins\). Such a file defines a Midi synth with its list of instrument and how to select them via Midi \(Bank Select/Program Change values\). JJazzLab ships with .ins files for a few existing harware synthesizers \(e.g. Yamaha Motif, Korg X-50, …\). If you don’t find an .ins file for your sound device, you can search the web or create your own \(google “Cakewalk Instrument Definition File” for help\).

One or more .ins files can be added from the Output Synth editor : 

## JJazzLab .ins format extensions <a id="jjazzlab-ins-format-extensions"></a>

The standard .ins file format lacks some information for JJazzLab to fully optimize instrument selection and drum notes remapping.

JJazzLab needs:

1. For melodic instruments: its _GM substitute_ instrument  Example: the _GM substitute_ for the XG instrument ‘12 String Guitar’ is the GM instrument ‘Steel Guitar’
2. For percussion instruments/drum kits: its _type_ and its _drum key map_ 

Therefore some \(optional\) extensions have been introduced, as show in the examples below.

```text
;
; {{ SubGM1= }}
;
[PRE1]
0=Pn:Full Concert Grand {{ SubGM1=0 }}       ; substitute = GM Acoustic Piano
1=Pn:Rock Grand Piano   {{ SubGM1=1 }}       ; substitute = GM Bright Piano 
2=Pn:Mellow Grand Piano {{ SubGM1=0 }}       ; substitute = GM Acoustic Piano
5=Pn:Aggressive Grand   {{ SubGM1=1 }}       ; substitute = GM Bright Piano
...
18=Pn:CP 1979           {{ SubGM1=3 }}       ; substitute = GM Electric Grand Piano
19=Pn:CP70 Chorus       {{ SubGM1=3 }}       ; substitute = GM Piano
...
```

```text
;
; {{ DrumKit=,  }}
;          : STANDARD, POWER, ROOM, ELECTRONIC, ANALOG, JAZZ, BRUSH, ORCHESTRA, SFX
;  : GM, GS_GM2, XG
;
[DR:PRE]
0=Dr:Power Standard Kit 1   {{DrumKit=POWER, XG}} 
1=Dr:Power Standard Kit 2   {{DrumKit=POWER, XG}} 
2=Dr:Hyper Standard Kit     {{DrumKit=STANDARD, XG}} 
3=Dr:Dry Standard Kit       {{DrumKit=ROOM, XG}} 
...
```

```text
;
; {{ UseGsInstruments }}       => For melodic instrument selection a GS Sysex message will be sent to make sure channel is in melodic mode
; {{ UseGsDrumsInstruments }}  => For drums instrument selection a GS Sysex message will be sent to make sure channel is in percussion mode
;
[JJazzLab SoundFont (GS)]
BankSelMethod=1                                ; Use Bank Select MSB only
Patch[0]=GM Bank  {{ UseGsInstruments }}       ; This bank stores GS melodic instruments
Patch[128]=Bank 1 {{ UseGsInstruments }}       ; This bank stores GS melodic instruments 
Patch[256]=Bank 2 {{ UseGsInstruments }}       ; This bank stores GS melodic instruments
...
Patch[*]=Drums    {{ UseGsDrumsInstruments }}  ; This bank stores GS drums instruments
...
```

If you have a custom .ins file for your synth, then you should use these extensions in order to fully benefit from the JJazzLab features.

