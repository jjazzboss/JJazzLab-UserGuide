---
description: Connecting JJazzLab to other synths via Midi.
---

# Other synths

In general we recommend to use [FluidSynth](using-fluidsynth.md): no setup and decent sounds.&#x20;

But if you have a high-quality hardware or software synth (VST, AU, AAX, ...), you can use it with JJazzLab via a Midi cable or a a virtual Midi cable/device (such as LoopMIDI for Windows).

![Connecting a Midi synth to JJazzLab](<../.gitbook/assets/MidiWizard-image1 (1).png>)

In the **Midi** tab of the **Options/Preferences :**

* Unselect "use FluidSynth"
* Select a Midi OUT device
* Select an Output Synth which describes the capabilities of the connected synth.&#x20;

The **Output Synth** information enables JJazzLab to directly control your synth from the mix console. It is also used to automatically select the appropriate sounds when using a new rhythm, or to remap drums notes when needed (Yamaha styles use XG drum maps, but your synth may not).

There is a predefined list of Output Synths as shown below. If you synth has more capabilities, you can use "**Add a synth from file...**" to load a Midi synth definition file (.ins).

<figure><img src="../.gitbook/assets/2023-12-31 18_23_58-Options.png" alt=""><figcaption></figcaption></figure>

## Midi synth definition files (.ins)

JJazzLab can read **Cakewalk instrument definition files** (.ins). Those files are used by many DAWs, search the web for more information about the .ins format.

An **.ins** file defines a **Midi synth** with its list of instruments and how to select them via Midi (Bank Select/Program Change values).

### JJazzLab .ins format extensions <a href="#jjazzlab-ins-format-extensions" id="jjazzlab-ins-format-extensions"></a>

{% hint style="info" %}
These .ins format extensions are not mandatory to use for JJazzLab to work. But they are required if you have a custom .ins file and want to fully benefit from the JJazzLab features in order to get better sounding backing tracks.
{% endhint %}

The standard .ins file format lacks some information for JJazzLab to fully optimize instrument selection and **drum map** conversion.

For an optimum use JJazzLab needs:

1. For melodic instruments: its **GM substitute** instrument\
   &#x20;Example: the **GM substitute** for the XG instrument ‘12 String Guitar’ is the GM instrument ‘Steel Guitar’
2. For percussion instruments/drum kits: its **type** and its **drum key map**

Therefore some (optional) keyword extensions have been introduced, "\{{ xxxx \}}", as shown in the examples below.

```
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

```
;
; {{ DrumKit= type, keymap }}
;   type=STANDARD, POWER, ROOM, ELECTRONIC, ANALOG, JAZZ, BRUSH, ORCHESTRA, SFX
;   keymap=GM, GS_GM2, XG
;
[DR:PRE]
0=Dr:Power Standard Kit 1   {{DrumKit=POWER, XG}} 
1=Dr:Power Standard Kit 2   {{DrumKit=POWER, XG}} 
2=Dr:Hyper Standard Kit     {{DrumKit=STANDARD, XG}} 
3=Dr:Dry Standard Kit       {{DrumKit=ROOM, XG}} 
...
```

There are also 2 special keyword extensions if your synth is GS compatible:

```
; For GS-compatible synths only
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
