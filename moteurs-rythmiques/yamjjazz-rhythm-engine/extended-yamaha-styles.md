# Styles Yamaha étendus

Le [YamJJazz rhythm engine](./) peut lire un nouveau format de fichier (.yjz) qui étend les capacités d'un fichier de [style Yamaha](yamaha-styles.md) standard (.sty, .prs, .sst, etc.). L'objectif est de permettre la conception de rhythms avec une gamme dynamique plus large, des rhythms qui sonnent moins répétitifs.

Le fichier .yjz peut également être utilisé pour modifier simplement la musique d'un style Yamaha existant, comme le montre l'exemple ci-dessous.

Un **style étendu** (.yjz) supporte :

* **Nombre illimité de variations**\
  Au lieu de Main A/B/C/D, vous pouvez avoir Main A-1, Main A-2, Main B-1, Main B-2, Main B-3, Main C-1, Main C-2, …<br>
* **Nombre illimité de phrases sources pour chaque variation**\
  Avec un style Yamaha standard, la même phrase source est toujours utilisée pour une variation donnée. Les **phrases sources alternatives** permettent au concepteur de rhythms de définir des phrases différentes mais similaires pour, par exemple, Main A-1, qui seront utilisées aléatoirement par le YamJJazz engine afin de sonner moins répétitives.

{% hint style="warning" %}
Un fichier .yjz est juste la partie extension d'un fichier de style Yamaha standard, le **style de base**. Ainsi, lorsque vous lisez **MyRhythm.yjz**, YamJJazz doit trouver **MyRhythm.sty** (ou **MyRhythm.prs**) dans le même répertoire.
{% endhint %}

## Assistant de création de style étendu

Cet assistant, disponible dans le menu **Tools**, permet de créer un **fichier de style étendu** (.yjz) prêt à être personnalisé à partir d'un fichier de style Yamaha standard (.sty, .prs, ...). Voir la vidéo ci-dessous pour savoir comment l'utiliser.

{% hint style="warning" %}
Une fois créé, vous devrez modifier manuellement les phrases musicales du fichier Midi .yjz à l'aide d'un éditeur Midi ou d'un DAW comme Cubase, Ableton Live, etc. Sinon, le nouveau style étendu sonnera exactement comme le style de base.
{% endhint %}

### Exemple simple : modifier le Main A d'un style Yamaha existant

Disons que vous voulez changer la musique de la variation **Main A** du style Yamaha **MediumJazzS737.sst**.

Lancez l'**assistant de création de style étendu**, sélectionnez le rhythm **MediumJazzS737.sst**, puis ajustez les paramètres comme indiqué sur l'image ci-dessous.

<figure><img src="../../.gitbook/assets/2023-01-03 16_45_42-Extended style creation wizard.png" alt=""><figcaption><p>Paramètres de l'assistant pour modifier uniquement la section Main-A, sans phrases sources alternatives.</p></figcaption></figure>

Une fois **MediumJazzS737-ext.yjz** généré, ouvrez-le dans votre éditeur Midi. Si vous utilisez Cubase par exemple, vous devriez voir quelque chose comme ceci :

<figure><img src="../../.gitbook/assets/2023-01-03 16_59_55-Cubase AI 7 - [Cubase AI 7 Project - Untitled1].png" alt=""><figcaption></figcaption></figure>

Vous pouvez maintenant modifier les phrases source Midi comme vous le souhaitez, en fonction de l'accord source fourni dans le nom de la piste (par exemple, C7M pour les pistes de basse). _Vous ne devez pas changer les noms des pistes ou changer la durée de la section_ (8 mesures/32 temps ici).

{% hint style="info" %}
Vous pouvez voir plusieurs phrases sources pour un instrument. Dans notre exemple, il y a 2 pistes pour la basse. Vous devez apporter des modifications cohérentes à chacune d'elles.&#x20;

La raison pour laquelle cela se produit dans les styles Yamaha dépasse la portée de ce tutoriel. L'idée générale est d'autoriser des phrases spécialisées pour des cas spécifiques, par exemple une phrase pour les accords mineurs et une autre pour les accords majeurs. Recherchez la section CASM du style Yamaha si vous souhaitez plus d'informations.
{% endhint %}

Lorsque l'édition Midi est terminée, enregistrez votre fichier.&#x20;

Dans JJazzLab, démarrez un **Rescan** dans Options/Rhythms.

Vous pouvez maintenant utiliser le nouveau style modifié dans votre song : sélectionnez simplement **MediumJazzS737-ext.yjz** depuis les **YamJJazz extended styles** comme indiqué ci-dessous.&#x20;

<figure><img src="../../.gitbook/assets/2023-01-03 17_49_15-JJazzLab  3.2.1.png" alt=""><figcaption></figcaption></figure>

## Video tutorial

{% embed url="https://youtu.be/2iVB8t6uAVA" %}

## Format de fichier .yjz <a href="#yjz-extension-file-format" id="yjz-extension-file-format"></a>

{% hint style="info" %}
Si vous ne prévoyez pas de créer votre propre fichier .yjz, vous pouvez ignorer ce paragraphe.
{% endhint %}

Nous vous recommandons d'utiliser l'**assistant de création de style étendu** pour préparer un fichier .yjz prêt à être personnalisé (voir ci-dessus).

Le fichier d'extension (.yjz) doit être associé à un fichier de style Yamaha de base (.sty, .prs, .sst, etc.) avec le même nom dans le même répertoire.

### Aperçu <a href="#overview" id="overview"></a>

YamJJazz lit d'abord le fichier de **style de base** pour obtenir les informations de style Yamaha suivantes :

* Données CASM : paramètres des canaux pour chaque variation disponible (canaux Midi utilisés, accords sources, limites de notes inférieures/supérieures, canaux d'accords/mélodie, etc.)
* Données SINT : paramètres des instruments (sélection de banque/changement de programme, volume, …)
* Données musicales : les phrases sources Midi pour chaque canal de chaque variation disponible

Ensuite, YamJJazz lit le fichier d'extension .yjz pour obtenir les phrases sources Midi utilisées pour affiner les variations de base disponibles et pour ajouter des phrases sources alternatives.

Si le style de base utilise la variation Main A (exemple), il est alors possible de définir des variations Main A-1, Main A-2, Main A-3, etc. dans le fichier d'extension. Le nombre est appelé le niveau de complexité. Dès que vous définissez une variation Main A-x dans le fichier d'extension, elle remplace la variation Main A originale du fichier de base.

Si le fichier de base définit la variation Main D (exemple) mais que le fichier d'extension ne définit pas Main D-x, alors le Main D original sera utilisé avec le nom Main D-1.

{% hint style="danger" %}
Si le style de base n'a pas de variation Intro B (exemple), il **n'est pas possible** de définir Intro B-x dans le fichier d'extension.
{% endhint %}

### Format Midi <a href="#midi-format" id="midi-format"></a>

**Les fichiers .yjz utilisent le format Midi 1**, ils contiennent plusieurs pistes. Notez que les fichiers .sty ou .prs utilisent le **format Midi 0**, ils contiennent une seule piste.

Chaque piste du fichier d'extension doit commencer par un méta-événement de nom de piste Midi avec la syntaxe suivante :

**`trackname=<base variation>-<complexity level>-<id string>-<phrase length in beats>`**

Exemples de noms de piste :

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

Pour `<id string>`, vous pouvez utiliser la chaîne de votre choix, mais il est recommandé de mentionner au moins l'instrument cible. Si vous utilisez l'**assistant de création de style étendu**, la chaîne d'identification est générée pour vous et sera quelque chose comme `[Bass, C7M, ch11]` : le nom de l'instrument, l'**accord source** et le **canal Midi source**.

Toutes les pistes d'une variation donnée doivent avoir la même longueur en temps. Mais différentes variations peuvent avoir des longueurs différentes.

{% hint style="warning" %}
Selon les données CASM, il peut y avoir plus d'une phrase source pour un instrument donné (les phrases guitar et guitar\_root dans l'exemple ci-dessus). Par exemple, un canal peut être utilisé pour les accords majeurs, l'autre pour les accords mineurs.
{% endhint %}

Une piste ne doit contenir que des messages Midi note on/off pour son **accord source** et son **canal Midi source**, tels que définis dans les données CASM du style de base. Si vous avez utilisé l'**assistant de création de style étendu**, l'accord source et le canal Midi sont indiqués dans la chaîne `<id string>`, comme expliqué ci-dessus.

### Phrases sources alternatives <a href="#alternate-takes" id="alternate-takes"></a>

Pour ajouter des **phrases sources alternatives** pour une variation donnée, ajoutez simplement des phrases sources à la suite de chaque piste de cette variation. Chaque phrase source ajoutée doit avoir la même longueur que la phrase originale.

**Exemple**\
La longueur de la phrase source de la piste Main A-1-bass-8 est de 8 temps (2 mesures en 4/4). Vous pouvez ajouter 2 phrases sources similaires de 8 temps sur cette piste, de sorte que la longueur de la piste devienne 24 temps. YamJJazz considérera les 2 phrases ajoutées comme des **phrases sources alternatives** de la première phrase source, à utiliser aléatoirement lors du rendu de la partie basse Main A-1.&#x20;

Notez que 2 phrases sources alternatives doivent également être ajoutées pour toutes les autres pistes Main A-1 : Main A-1-drums-8, Main A-1-guitar-8 et Main A-1-guitar\_root-8.

{% hint style="info" %}
Si vous avez par exemple 3 phrases sources pour Main A-1, JJazzLab choisira au hasard une phrase source toutes les 2 mesures. La sélection n'est en fait pas aléatoire à 100% : la première phrase source a plus de chances d'être sélectionnée que la seconde, et la seconde a plus de chances d'être sélectionnée que la troisième, etc. En d'autres termes, la dernière phrase source a le moins de chances d'être sélectionnée.
{% endhint %}
