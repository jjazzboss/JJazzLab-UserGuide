---
description: Comment installer JJazzLab.
---

# Instructions d'installation

## Configuration requise

JJazzLab nécessite au minimum **Java 11** (ou ultérieur) installé sur votre ordinateur.&#x20;

{% hint style="info" %}
Si vous n'avez pas Java installé, utilisez le programme d'installation JJazzLab avec Java intégré (option recommandée, téléchargement plus volumineux).
{% endhint %}

## Windows

Téléchargez et exécutez le [**programme d'installation JJazzLab pour Windows**](https://sourceforge.net/projects/jjazzlab/files/) (choisissez la dernière version pour votre matériel).

## MacOS

Téléchargez et exécutez le [**programme d'installation JJazzLab pour Mac**](https://sourceforge.net/projects/jjazzlab/files/).

## Linux

Téléchargez et exécutez le [**programme d'installation JJazzLab pour Linux**](https://sourceforge.net/projects/jjazzlab/files/) (choisissez la dernière version pour votre matériel).

Notez que JJazzLab nécessite la configuration d'un périphérique Midi. Sous Linux, vous pouvez utiliser **Timidity++** ou un périphérique Midi natif.

## Vérifier l'installation

1. Lancez JJazzLab
2. Chargez un fichier song (utilisez **File/Open Songs...**) et ouvrez-en un depuis le dossier **ExampleFiles**
3. Appuyez sur **Play**. Si vous entendez de la musique, l'installation est réussie !
4. Si vous n'entendez pas de musique, vérifiez :
   - **Tools/Options/Midi** : assurez-vous qu'un périphérique **Midi OUT** est sélectionné
   - Si vous utilisez FluidSynth : vérifiez l'onglet **FluidSynth** dans **Tools/Options/Midi** et assurez-vous qu'il est activé
   - Sinon, consultez les pages [FluidSynth](sons/using-fluidsynth.md) ou [Autres synthétiseurs](sons/other-synths.md)
