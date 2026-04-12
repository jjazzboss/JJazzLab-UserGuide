# Song and mix files

Lorsque vous enregistrez un morceau appelé **mySong**, JJazzLab enregistre en fait 2 fichiers différents :

* **mySong.sng** : contient tout sauf les informations de mixage, c'est-à-dire le lead sheet, la song structure et la référence au rhythm utilisé (ex. "16beat.s456.sty").
* **mySong.mix** : contient uniquement les informations de mixage, c'est-à-dire quel instrument est utilisé par chaque piste, et avec quelle configuration (volume, reverb, pan, ...).

Pourquoi utiliser 2 fichiers différents ?

Parce que les informations de mixage sont spécifiques à votre output synth ([FluidSynth](../sounds/using-fluidsynth.md) ou un [synthé personnalisé](../sounds/other-synths.md)). Intégrer les données de mixage dans le fichier .sng rendrait les fichiers .sng non portables entre utilisateurs, car les utilisateurs ont des output synths différents.

Lorsque vous ouvrez **mySong.sng**, JJazzLab essaie d'ouvrir **mySong.mix** dans le même répertoire. Si **mySong.mix** n'existe pas, JJazzLab crée le mix en utilisant le fichier de [default rhythm mix](song-and-mix-files.md#default-rhythm-mix) s'il est présent, sinon il utilise le **mix intégré du rhythm** (voir [ci-dessous](song-and-mix-files.md#default-rhythm-mix)).

{% hint style="warning" %}
Lors du chargement d'un fichier song (.sng), si le rhythm référencé (ex. "MediumJazz.s637.sst") n'est pas disponible, JJazzLab substitue un autre rhythm disponible sur le système. JJazzLab essaie de trouver un rhythm « similaire » basé sur le nom (un autre rhythm « jazz » dans l'exemple ci-dessus). S'il ne peut pas en trouver un approprié, il utilise simplement le rhythm par défaut pour la signature temporelle.
{% endhint %}

## Default rhythm mix

{% hint style="info" %}
Si vous utilisez souvent un certain rhythm, ajustez son mix et enregistrez-le comme **fichier de default rhythm mix**, de sorte que chaque fois que vous utiliserez ce rhythm dans un song, il sonnera de manière optimale pour votre output synth.
{% endhint %}

#### Fonctionnement

Lorsque vous créez un song et sélectionnez un nouveau rhythm (ex. `MediumJazz.s637.sst`), JJazzLab recherche un fichier de **default rhythm mix** (`MediumJazz.s637.mix`) pour initialiser le song mix de ce rhythm.

Le default rhythm mix vous permet de définir **un song mix optimisé adapté à votre output synth** ([FluidSynth](../sounds/using-fluidsynth.md) ou un [synthé personnalisé](../sounds/other-synths.md)) : par exemple avec `MediumJazz.s637.sst` vous pouvez rendre la guitare électrique moins forte, remplacer l'instrument de basse GM par défaut par un meilleur disponible sur votre synthé, et couper la flûte que vous n'aimez pas.

{% hint style="warning" %}
**Si le fichier de default rhythm mix n'est pas présent**, JJazzLab utilise le **mix intégré du rhythm**. Le mix intégré du rhythm est déduit des données du rhythm et des capacités de votre output synth. Avec FluidSynth le mix résultant devrait convenir avec quelques ajustements manuels. Avec un synthé personnalisé, il peut nécessiter plus de corrections.
{% endhint %}

#### Ajustement et sauvegarde d'un default rhythm mix

* Dans les options Midi, sélectionnez votre output synth préféré, ex. [FluidSynth](../sounds/using-fluidsynth.md).
* Chargez un song utilisant votre rhythm favori et jouez-le\
  (le song mix est initialisé avec le **mix intégré du rhythm** si aucun default rhythm mix n'est défini)
* Ajustez le mix jusqu'à être satisfait du rendu du song
* Utilisez **Save as default rhythm mix** depuis le **menu File de la Mix Console**, comme indiqué ci-dessous.

<figure><img src="../.gitbook/assets/2024-09-30 22_55_58-JJazzLab  4.1.2-SNAPSHOT.png" alt=""><figcaption></figcaption></figure>

Le fichier de default rhythm mix est enregistré **dans le même répertoire que le fichier rhythm**.

{% hint style="success" %}
JJazzLab utilisera désormais automatiquement ce **default rhythm mix** chaque fois que vous sélectionnerez le rhythm correspondant dans un song.
{% endhint %}

S'il est défini, vous pouvez toujours réappliquer un default rhythm mix en utilisant **Load default rhythm mix** depuis le **menu File de la Mix console**.

Si vous souhaitez réinitialiser le song mix au **mix intégré du rhythm** (voir ci-dessus), utilisez **Reset channels** depuis le **menu Edit de la Mix Console**, comme indiqué ci-dessous.

<figure><img src="../.gitbook/assets/2024-09-30 22_26_48-JJazzLab  4.1.2-SNAPSHOT.png" alt=""><figcaption></figcaption></figure>

## Ordre de recherche des fichiers de mixage

En combinant les 2 paragraphes ci-dessus, voici comment JJazzLab recherche des informations de mixage lorsque vous chargez **myDir/mySong.sng** et que ce song utilise le rhythm **16BeatRock** :

1. utilise **myDir/mySong.mix** si présent<br>
2. utilise **defaultRhythmMixDir/16BeatRock.mix** si présent<br>
3. utilise le mix intégré par défaut de **16BeatRock**

Les étapes 2. et 3. sont également utilisées lorsque vous ajoutez un nouveau rhythm dans un song.
