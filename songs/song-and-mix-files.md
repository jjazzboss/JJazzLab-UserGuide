# Song and mix files

When you save a song called **mySong**, JJazzLab actually saves 2 different files:

* **mySong.sng**: contains everything except the mix information, i.e. the chord leadsheet, the song structure, the reference to the rhythm used (e.g. "16beat.s456.sty").
* **mySong.mix**: contains only the mix information, i.e. which instrument is used by each track, and with which configuration (volume, reverb, pan, ...).

Why using 2 different files ?&#x20;

Because the mix information is specific to your output synth ([FluidSynth ](../sounds/using-fluidsynth.md)or a [custom synth](../sounds/other-synths.md)). Integrating the mix data in the .sng file would make .sng files not portable between users, since users have different output synths.

When you open **mySong.sng**, JJazzLab also opens **mySong.mix** in the same directory. If **mySong.mix** does not exist then JJazzLab creates the mix using the [default rhythm mix](song-and-mix-files.md#default-rhythm-mix) if present, otherwise it infers the rhythm's builtin mix.

{% hint style="warning" %}
When loading a song file (.sng),  if the rhythm reference (e.g. "MediumJazz.s637.sst") used by this song is not available, JJazzLab substitutes another rhythm available on the system. JJazzLab tries its best to find a "similar" rhythm based on the name (another "jazz" rhythm in the example above). If it can't find a suitable rhythm, it just uses the default rhythm for the time signature.
{% endhint %}

## Default rhythm mix

{% hint style="info" %}
If you often use a certain rhythm, adjust its mix and save it as a **default rhythm mix file**, so that each time you'll use that rhythm in a song, it will sound optimally for your output synth.
{% endhint %}

#### How it works

When you create a song and select a new rhythm (e.g. `MediumJazz.s637.sst`), JJazzLab looks for a **default rhythm mix** file (`MediumJazz.s637.mix`) to initialize the song mix for this rhythm.&#x20;

The default rhythm mix lets you define **an optimized rhythm mix adapted to your output synth** ([FluidSynth ](../sounds/using-fluidsynth.md)or a [custom synth](../sounds/other-synths.md)): for example with`MediumJazz.s637.sst` you can make the electric guitar quieter, replace the default GM bass instrument by a better one available on your synth, and mute that flute you don't like.

{% hint style="warning" %}
**If the default rhythm mix file is not present**, JJazzLab uses the **rhythm's** **builtin mix**. The rhythm's builtin mix is infered from the rhythm data and from your output synth capabilities. With FluidSynth the resulting mix should be OK  with a few manual adjusments. With a custom synth, it might need more fixes.
{% endhint %}

#### Adjusting and saving a default rhythm mix

* In the Midi options select your preferred output synth, e.g. [FluidSynth](../sounds/using-fluidsynth.md).&#x20;
* Load a song which uses your favorite rhythm and play it\
  (song mix is initialized with the **rhythm's builtin mix** if no default rhythm mix is defined)
* Adjust the mix until you're satisfied with the song rendering
* Use **Save as default rhythm mix** from the **Mix Console File menu**, as shown below.

<figure><img src="../.gitbook/assets/2024-09-30 22_55_58-JJazzLab  4.1.2-SNAPSHOT.png" alt=""><figcaption></figcaption></figure>

The default rhythm mix file is saved **in the same directory than the rhythm file**.&#x20;

{% hint style="success" %}
JJazzLab will now automatically use this **default rhythm mix** each time you select the corresponding rhythm in a song.
{% endhint %}

If it's defined, you can always reapply a default rhythm mix using **Load default rhythm mix** from the **Mix console menu File**.&#x20;

If you want to reset the song mix to the **rhythm's builtin mix** (see above), use **Reset channels** from the **Mix Console Edit menu**, as shown below.&#x20;

<figure><img src="../.gitbook/assets/2024-09-30 22_26_48-JJazzLab  4.1.2-SNAPSHOT.png" alt=""><figcaption></figcaption></figure>

## Mix file lookup order

Combining the 2 paragraphs above, below is how JJazzLab looks for mix information when you load **myDir/mySong.sng** and this songs uses rhythm **16BeatRock** :

1. use **myDir/mySong.mix** if present\

2. use **defaultRhythmMixDir/16BeatRock.mix** if present\

3. use **16BeatRock** builtin default mix

Steps 2. and 3. are also used when you add a new rhythm in a song.
