# Extended Yamaha styles

The [YamJJazz rhythm engine](./) ****can read ****a new file format \(.yjz\) which extends the capabilities of a standard [Yamaha style](yamaha-styles.md) file \(.sty, .prs\). Objective is to enable the design of rhythms with a wider dynamic range, rhythms which sound less repetitive.

An **extended style** \(.yjz\) supports :

* **Unlimited number of variations** Instead of Main A, Main B, Main C, you can define Main A-1, Main A-2, Main B-1, Main B-2, Main B-3, Main C-1, Main C-2, … 
* **Unlimited "alternate takes" for each variation** With a standard Yamaha style the same phrase is always used for a given variation, let’s say Main A. **Alternate takes** lets the rhythm designer define different-but-similar phrases for Main A, which will be used randomly by the YamJJazz engine in order to sound less repetitive.

{% hint style="warning" %}
A .yjz file is just the extension part of a standard Yamaha style file, the **base style**. So when you read **MyRhythm.yjz**, YamJJazz needs to find **MyRhythm.sty** \(or **MyRhythm.prs\)** in the same directory.
{% endhint %}

## Extended style creation wizard

This wizard, available in the **Tools** menu, is used to create a ready-to-be-customized **extended style file** \(.yjz\) for a standard Yamaha style file \(.sty, .prs, ...\). 

{% hint style="warning" %}
Once created you'll need to manually alter the musical phrases of the .yjz file using a DAW like Cubase, Ableton Live, etc. Otherwise the new extended style will sound exactly like the base style.
{% endhint %}

## .yjz extension file format <a id="yjz-extension-file-format"></a>

{% hint style="info" %}
If you don’t plan to create your own .yjz file you can skip this information.
{% endhint %}

The extension file \(.yjz\) must be associated to a base Yamaha style file \(.sty or .prs\) with the same name in the same directory.

### Overview <a id="overview"></a>

YamJJazz first reads the base style file to get the following information:

* CASM data: channels parameters for each available variation \(Intro A, Main A, Main B, …\)
* SINT data: instruments parameters \(bank select/program change, volume, …\)
* Musical data: the Midi source phrases for each channel of each available variation

Then YamJJazz reads the .yjz extension file to get Midi source phrases used to refine the available base variations and to add ‘alternate takes’ source phrases.

If the base style uses variation e.g. Main A, then it’s possible to define variations Main A-1, Main A-2, Main A-3, etc in the extension file. The number is called the complexity level. As soon as you define a Main A-x variation in the extension file, it replaces the original Main A variation from the base file.

If the base file defines variation e.g. Main D but the extension file does not define Main D-x, then the original Main D will be used with the name Main D-1.

If the base style does not use variation e.g. Intro B, then it’s not possible to define Intro B-x in the extension file.

### Midi format <a id="midi-format"></a>

.yjz files use Midi format 1, they can contain several tracks. Note that .sty or .prs files use Midi format 0, they contain a single track.

Each track of the extension file must start with a Midi trackname meta event with the following syntax:

**`trackname=<base variation>-<complexity level>-<id string>-<phrase length in beats>`**

Examples:

* Main A-1-drums-8
* Main A-1-bass-8
* Main A-1-guitar-8
* Main A-1-guitar\_root-8
* Main A-2-drums-8
* Main A-2-bass-8
* Main A-2-guitar-8
* Main A-2-guitar\_root-8
* Ending B-1-piano-4
* Ending B-1-bass-4

All tracks for a given variation must have the same length in beats. But different variations can have different lengths.

Depending on the CASM data, there might be one or more source phrases for a given destination channel \(the guitar and guitar\_root phrases in the example above\).

A track should contain only Midi note on/off messages for one Midi channel. It must be the source channel defined by the CASM data for the target instrument represented by the id string. For example, if the CASM data says that Midi channel 11 is the only source channel for the bass of variation Main A, then the Main A-1-bass-8 should contain only notes for channel 11.

### Alternate takes <a id="alternate-takes"></a>

To add ‘alternate takes’ for a given variation, just append source phrases on each track of this variation. Each appended source phrase must have the same length than the original phrase.

**Example**  
The source phrase length of track Main A-1-bass-8 is 8 beats. You can append 2 similar 8-beat source phrases on that track, so the track length becomes 24 beats. YamJJazz will consider the 2 appended phrases as ‘alternate takes’ of the first source phrase, to be used randomly when rendering the Main A-1 bass part. Note that 2 ‘alternate takes’ must be also added for all the other Main A-1 tracks: Main A-1-drums-8, Main A-1-guitar-8 and Main A-1-guitar\_root-8.

