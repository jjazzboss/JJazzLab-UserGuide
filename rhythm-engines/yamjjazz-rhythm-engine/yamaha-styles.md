# Yamaha styles

The [YamJJazz ](./)engine is able to read all Yamaha style files \(.sty, .prs, .bcs, .sst, at SFF1 or SFF2 format\). You can find thousands of style files on the web, most of them for free. Visit the [resources](https://www.jjazzlab.com/en/resources) page for useful links.

Yamaha styles usually have 4 variations _Main A, Main B, Main C, Main D_, plus some _Intros_ and _Endings_. Each variation can use tracks of the following types:

* **Rhythm** \(e.g. drums\)
* **Sub-rhythm** \(e.g. percussion\)
* **Bass**
* **Chord1** \(e.g. guitar\)
* **Chord2** \(e.g. keyboard\)
* **Pad** \(e.g. strings\)
* **Phrase1** \(e.g. Brass\)
* **Phrase2**

## Yamaha "Mega Voices”, “Super Articulation Voices”, ... <a id="yamaha-specific-voices-mega-voices-super-articulation-voices"></a>

Yamaha style files are optimized for Yamaha arranger keyboards. The latest models \(Tyros, Genos…\) has many voices with special features \(e.g "Mega Voices"\), especially for guitars which are optimized for style rendering.

Other keyboards or SoundFonts \(including the JJazzLab SoundFont\) can’t reproduce these special voices correctly. That’s why some recent Yamaha style files \(SFF2 format\) may not sound right with JJazzLab. If this happens locate the faulty channels using the Solo button in the MixConsole, and lower their volume or mute them.

## Limitations <a id="limitations"></a>

JJazzLab is designed to host any kind of rhythm generation engines, and they must work with any kind of output synth, not only the Yamaha keyboards. Therefore some specific Yamaha style file features are not supported:

* SysEx Midi messages: ignored.
* Controller messages: ignored.
* Per-variation sounds: ignored, YamJJazz uses the style’s default sounds for all variations.
* Yamaha Mega Voices : non musical notes or sound effects \(notes above C6\) are ignored.
* Pitch bend Midi messages : ignored.
* OTS and MDB sections: ignored.

