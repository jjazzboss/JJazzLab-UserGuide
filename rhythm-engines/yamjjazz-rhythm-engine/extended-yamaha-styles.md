# Extended Yamaha styles

The [YamJJazz rhythm engine](./) can read a new file format (.yjz) which extends the capabilities of a standard [Yamaha style](yamaha-styles.md) file (.sty, .prs, .sst, etc.). Objective is to enable the design of rhythms with a wider dynamic range, rhythms which sound less repetitive.

.yjz file can also be used to simply modify the music of an existing Yamaha style, as show in the example below.

An **extended style** (.yjz) supports :

* **Unlimited number of variations**\
  Instead of Main A/B/C/D, you can have Main A-1, Main A-2, Main B-1, Main B-2, Main B-3, Main C-1, Main C-2, …<br>
* **Unlimited number of source phrases for each variation**\
  With a standard Yamaha style the same source phrase is always used for a given variation.  **Alternate source phrases** lets the rhythm designer define different-but-similar phrases for e.g Main A-1, which will be used randomly by the YamJJazz engine in order to sound less repetitive.

{% hint style="warning" %}
A .yjz file is just the extension part of a standard Yamaha style file, the **base style**. So when you read **MyRhythm.yjz**, YamJJazz needs to find **MyRhythm.sty** (or **MyRhythm.prs)** in the same directory.
{% endhint %}

## Extended style creation wizard

This wizard, available in the **Tools** menu, is used to create a ready-to-be-customized **extended style file** (.yjz) from a standard Yamaha style file (.sty, .prs, ...). See the  video below for how to use it.

{% hint style="warning" %}
Once created you'll need to manually alter the musical phrases of the .yjz Midi file using a Midi editor or a DAW like Cubase, Ableton Live, etc. Otherwise the new extended style will sound exactly like the base style.
{% endhint %}

### Simple example : modify Main A of an existing Yamaha style

Say you want to change the music of the **Main A** variation of Yamaha style **MediumJazzS737.sst**.

Start the **Extended style creation wizard**, select the rhythm **MediumJazzS737.sst**, then adjust the settings as shown on the image below.

<figure><img src="../../.gitbook/assets/2023-01-03 16_45_42-Extended style creation wizard.png" alt=""><figcaption><p>Wizard settings to alter only the Main-A section, with no alternate source phrases.</p></figcaption></figure>

Once **MediumJazzS737-ext.yjz** is generated, open it in your Midi editor. If you use Cubase for example, you should see something like this:

<figure><img src="../../.gitbook/assets/2023-01-03 16_59_55-Cubase AI 7 - [Cubase AI 7 Project - Untitled1].png" alt=""><figcaption></figcaption></figure>

Now you can modify the Midi source phrases as you want, based on the source chord provided in the track name (e.g. C7M for the bass tracks). _You must not change the track names or change the duration of the section_ (8 bars/32 beats here).

{% hint style="info" %}
You may see several source phrases for one instrument. In our example there are 2 tracks for the Bass. You should make consistent changes to each of them.&#x20;

The reason why this happens in Yamaha styles is beyond the scope of this tutorial. The general idea is to allow specialized phrases for specific cases, e.g. a phrase for minor chords and another one for major chords. Search for the Yamaha style CASM section if you want more information about this.
{% endhint %}

When the Midi editing is complete, save your file.&#x20;

In JJazzLab start a **Rescan** in Options/Rhythms.

Now you can use the new modified style in your song, just select **MediumJazzS737-ext.yjz** from the **YamJJazz extended styles** as seen below.&#x20;

<figure><img src="../../.gitbook/assets/2023-01-03 17_49_15-JJazzLab  3.2.1.png" alt=""><figcaption></figcaption></figure>

## Video tutorial

{% embed url="https://youtu.be/2iVB8t6uAVA" %}

## .yjz file format <a href="#yjz-extension-file-format" id="yjz-extension-file-format"></a>

{% hint style="info" %}
If you don’t plan to create your own .yjz file you can skip this paragraph.
{% endhint %}

We recommend to use the **Extended style creation wizard** to prepare a .yjz file ready to be customized (see above).

The extension file (.yjz) must be associated to a base Yamaha style file (.sty, .prs, .sst, etc.) with the same name in the same directory.

### Overview <a href="#overview" id="overview"></a>

YamJJazz first reads the **base style** file to get the following Yamaha style information:

* CASM data: channels parameters for each available variation (used Midi channels, source chords, lower/upper note limits, chord/melody channels, etc.)
* SINT data: instruments parameters (bank select/program change, volume, …)
* Musical data: the Midi source phrases for each channel of each available variation

Then YamJJazz reads the .yjz extension file to get Midi source phrases used to refine the available base variations and to add alternate source phrases.

If the base style uses variation Main A (example), then it’s possible to define variations Main A-1, Main A-2, Main A-3, etc. in the extension file. The number is called the complexity level. As soon as you define a Main A-x variation in the extension file, it replaces the original Main A variation from the base file.

If the base file defines variation Main D (example) but the extension file does not define Main D-x, then the original Main D will be used with the name Main D-1.

{% hint style="danger" %}
If the base style does not have variation Intro B (example), then it’s **not** possible to define Intro B-x in the extension file.
{% endhint %}

### Midi format <a href="#midi-format" id="midi-format"></a>

**.yjz files use Midi format 1**, they contain several tracks. Note that .sty or .prs files use Midi format 0, they contain a single track.

Each track of the extension file must start with a Midi trackname meta event with the following syntax:

**`trackname=<base variation>-<complexity level>-<id string>-<phrase length in beats>`**

Trackname examples:

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

For `<id string>` you can use whatever string you like, but it's a good practice to mention at least the target instrument. If you use the **Extended style creation wizard**, `id string` is generated for you and will be something like `[Bass, C7M, ch11]` : the instrument name, the **source chord** and **source Midi channel**.

All tracks for a given variation must have the same length in beats. But different variations can have different lengths.

{% hint style="warning" %}
Depending on the CASM data, there might be more than one source phrase for a given instrument (the guitar and guitar\_root phrases in the example above). For example one channel can be used for major chords, the other one for minor chords.
{% endhint %}

A track should only contain Midi note on/off messages for its **source chord** and **source Midi channel,** as defined in the CASM data of the base style. If you used the **Extended style creation wizard**, you have the **source chord** and **Midi channel** indicated in the `<id string>`, as explained above.

### Alternate source phrases <a href="#alternate-takes" id="alternate-takes"></a>

To add **alternate source phrases** for a given variation, just append source phrases on each track of this variation. Each appended source phrase must have the same length than the original phrase.

**Example**\
The source phrase length of track Main A-1-bass-8 is 8 beats (2 bars in 4/4). You can append 2 similar 8-beat source phrases on that track, so the track length becomes 24 beats. YamJJazz will consider the 2 appended phrases as **alternate source phrases** of the first source phrase, to be used randomly when rendering the Main A-1 bass part.&#x20;

Note that 2 alternate source phrases must be also added for all the other Main A-1 tracks: Main A-1-drums-8, Main A-1-guitar-8 and Main A-1-guitar\_root-8.

{% hint style="info" %}
If you have for example 3 source phrases for Main A-1, JJazzLab will randomly pick a source phrase every 2 bars. The selection is actually not 100% random: the first source phrase has more chances to be selected than the second one, and the second one has more chances to be selected than the third one, etc. In other words the last source phrase has the least chances to get selected.
{% endhint %}
