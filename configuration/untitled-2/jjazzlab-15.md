# JJazzLab

The rhythms are made available by rhythm generation engines.

Thanks to its open-source and pluggable architecture, JJazzLab can host many different rhythm generation engines. If you’re a developer you can build your own quite easily!

A rhythm generation engine has one or more _rhythm providers_ which propose a list of supported rhythms and the supported _rhythm parameters_. You can see the list of all available _rhythm providers_ in the rhythm selection dialog.

JJazzLab currently includes one rhythm generation engine, [YamJJazz](https://www.jjazzlab.com/en/doc/yamjjazz), which is based on Yamaha styles. Its _rhythm parameters_ are “Variation”, “Intensity” and “Fill” \(other parameters such as Mute or Tempo Factor are generic and work with any rhythm\).

## Future rhythm generation engines <a id="future-rhythm-generation-engines"></a>

Here some examples of what could be developed using the JJazzLab-X infrastructure.

* An AI-based jazz oriented engine with only one versatile rhythm which adapts to different contexts, like a real band \(slow or fast tempo, walking bass or not, etc.\).
* A drum engine similar to the Logic Pro X virtual drummer
* An engine able to adapt the backing track to a given melody
* A “meta-engine” which lets you combine individual tracks from various rhythms \(e.g. combine a hip-hop bass line with latin drums\)
* An engine able to read style files from Band-In-A-Box or other arranger keyboards such as Korg or Ketron
* etc.

