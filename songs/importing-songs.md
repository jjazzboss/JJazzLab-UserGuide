---
description: >-
  JJazzLab peut importer des morceaux depuis différents types de fichiers via le menu File/Import
  songs...
---

# Importation de morceaux

## Mode de conversion par lots

Si vous avez de nombreux fichiers à importer, vous devriez utiliser le **mode de conversion par lots**. Ce mode importe et convertit directement en fichiers .sng, sans ouvrir les fichiers importés dans JJazzLab. Les fichiers .sng créés seront situés dans le même répertoire que les fichiers importés.

Pour activer le **mode de conversion par lots**, cochez la case correspondante dans la boîte de dialogue **Import Songs...**, comme indiqué ci-dessous :

<figure><img src="../.gitbook/assets/2024-12-30 11_57_22-JJazzLab  4.1.2.png" alt=""><figcaption></figcaption></figure>

## Fichiers de morceaux Band In A Box (.SGU etc.)

JJazzLab peut importer des fichiers de morceaux .SG\* ou .MG\*.

Seules les données Band-In-A-Box suivantes sont utilisées pour générer le morceau JJazzLab correspondant :

* **song structure** : début du refrain, fin du refrain, nombre de refrains, tag after, tag start, tag end, fin à 2 mesures
* **chord symbols** : nom, position (y compris les paramètres push facultatifs), paramètres rest/hold/shot
* **paramètres du song** : autoriser push/rest dans le premier/milieu/dernier refrain.

La fonction d'importation de morceaux n'est pas fiable à 100%, mais la plupart des fichiers devraient convenir.

{% hint style="danger" %}
**Par défaut, les songs importés seront en 4/4**. Si vous savez que le morceau importé est en 3/4, une fois l'importation terminée, sélectionnez simplement la signature temporelle initiale et utilisez le menu contextuel **Set time signature** pour corriger la signature temporelle.
{% endhint %}

## Fichiers musicXML (.xml, .mxl, musicxml)

JJazzLab peut importer des fichiers musicXML (.xml, .musicxml) ou musicXML compressé (.mxl). Il a été testé avec succès avec des fichiers musicXML exportés depuis iRealPro.

Ce qui est importé :

* Chord symbols
* Signatures temporelles
* Titres de sections tels que "INTRO", "A", "B" trouvés dans les éléments **direction/direction-type/rehearsal**.
* Répétitions, fins (1. 2. 3...), tocoda, coda, segno, DC al coda, DC al fine, DS al coda, DS al fine, tels que trouvés dans les éléments **sound** et **barline**.
* Informations de style musical trouvées dans le type **groove** d'un élément **play/other-play**.

## Fichiers texte (.txt)

JJazzLab peut lire des accords depuis des fichiers texte. 3 formats sont pris en charge : GRID-BASED, TIME-BASED, BEAT-BASED.

#### **GRID-BASED : ex. "| 3/4 Bb7M | D7#5 | Eb7M | Db7#11 |"**

`!` peut être utilisé à la place de `|`. `%` répète la mesure précédente. N'importe quelle mesure peut commencer par une signature temporelle.

Exemple :

`|3/4 Bb7M | D7#5 | Eb7M | Db7#11 |`\
`| Cm7 | G7 | C7M | |`\
`|4/4 Fm7 | Gm7 C7 | % | F7M |`

{% hint style="success" %}
Ce format est compatible avec les fichiers texte exportés depuis **ChordPulse**.
{% endhint %}

#### **TIME-BASED : "pos\_in\_seconds, chord\_symbol"**

La signature temporelle et le tempo doivent être définis d'abord pour que pos\_in\_seconds puisse être converti en mesure/temps. S'ils ne sont pas définis, les valeurs par défaut sont 4/4 et 120 bpm.

Exemple :\
`timeSignature=3/4`\
`tempoBPM=60`\
`0, C`\
`3, F7`\
`4.5, Eb7`\
`6, D7`

#### **BEAT-BASED : "bar, beat, chord-symbol"**

Par défaut, bar et beat sont attendus en base 0 (la première mesure du song est la mesure 0). Vous pouvez changer cela en ajoutant "`useBase1`" au début du fichier, alors bar et beat sont attendus en base 1.

Exemple :\
`0, 0, C`\
`1, 0, F7`\
`1, 1.5, Eb7`\
`2, 0, D7`

#### **Autres informations sur le format texte**

* Les lignes commençant par `//` sont ignorées (commentaires)
* "`title=Mon nom de song`" : si spécifié, le song créé utilisera ce titre comme nom
* Les délimiteurs acceptés sont `,` `;` ou espace ou tabulation (format time ou beat-based)

## Fichiers lead sheet Impro-Visor (.ls)

JJazzLab peut importer des fichiers lead sheet Impro-Visor (.ls).

L'importation est limitée aux signatures temporelles et aux chord symbols.
