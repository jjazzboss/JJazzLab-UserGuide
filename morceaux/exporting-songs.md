# Exportation de morceaux

Le fichier exporté tient compte de la configuration de lecture actuelle :

* Configuration de l'[output synth](../sons/other-synths.md)
* Paramètres de la [mix console](../editeurs/mix-console.md) tels que l'instrument de la piste, le volume, l'état de sourdine, etc.
* Paramètres de [precount, click et tempo](../controle-de-lecture/commands.md)
* Les paramètres de [transposition des chord symbols à la lecture](../outils/chord-symbols-transposition.md)

## Exporter en Midi

Vous pouvez exporter un song entier en Midi via le menu **File/Export to Midi file...**

Vous pouvez également exporter des pistes individuelles en [faisant glisser avec la souris depuis la Mix Console](../editeurs/mix-console.md#export-to-midi-file-with-mouse-drag-and-drop).

#### Format du fichier Midi

Le fichier exporté est un fichier Midi multi-pistes de type 1.

Chaque piste d'instrument (à partir de la piste 1) est initialisée en utilisant le paramètre de piste de la mix console correspondant. La piste 0 contient :

* Si nécessaire, les messages d'initialisation Midi GM/GM2/GS/XG (dépend de la configuration de l'output synth)
* Les événements de tempo et de signature temporelle
* Les marqueurs pour les chord symbols

## Exporter en audio

Vous pouvez exporter le song entier en fichier **.wav** ou **.mp3** via le menu **File/Export to Audio file...**

{% hint style="danger" %}
L'export audio n'est disponible que si vous utilisez l'[output synth FluidSynth](../sons/using-fluidsynth.md) interne.
{% endhint %}

Cochez l'option **Separate tracks** pour exporter un fichier audio par piste, comme indiqué ci-dessous.

<figure><img src="../.gitbook/assets/2024-12-06 18_39_56-Export to audio file.png" alt=""><figcaption></figcaption></figure>
