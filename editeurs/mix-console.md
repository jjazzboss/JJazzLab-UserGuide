# Mix console

Utilisez la **mix console** pour :

* Changer les instruments
* Ajuster les paramètres de canal : volume, réverbération, chorus, panoramique, transposition, décalage de vélocité
* Couper ou mettre en solo des canaux
* Ajouter des user tracks
* Charger/enregistrer un fichier .mix
* Et plus encore : changer de canal Midi, utiliser des commandes Midi spéciales, exporter vers un fichier Midi, etc.

JJazzLab utilise les informations de la **mix console** pour envoyer les messages Midi pertinents au output synth. Cela se produit chaque fois que vous apportez une modification dans la mix console, ou lorsque vous démarrez la lecture.

{% hint style="danger" %}
Le Midi ne dispose que de 16 canaux Midi&#x73;**.** C'est pourquoi un song ne peut généralement pas avoir plus de 2 rhythms.
{% endhint %}

![](<../.gitbook/assets/2023-12-31 21_37_13-JJazzLab  4.0.2.png>)

Chaque piste de la mix console possède un **composant de vue d'ensemble** en bas qui représente les notes de la piste.

## Barre d'outils de la mix console

![](../.gitbook/assets/MixConsoleToolbar.png)

* **Master volume** : augmente ou diminue les messages de volume Midi
* **M** : couper ou activer le son de toutes les pistes
* **S** : désactiver toutes les pistes en solo
* **Panic** : envoyer un message de panique Midi, désactivant toutes les notes
* **Ajouter un user track** : voir [User tracks](mix-console.md#user-tracks) ci-dessous.

## Barre de menus de la mix console

### Menu File

*   **Load/Save Default Rhythm Mix** &#x20;

    Met à jour le song mix courant en chargeant le fichier de rhythm mix par défaut. \
    Ou enregistre le song mix courant comme fichier de rhythm mix par défaut : il sera réutilisé par défaut chaque fois que vous créerez un song utilisant le même rhythm. En savoir plus sur les [fichiers de rhythm mix par défaut](../morceaux/song-and-mix-files.md#default-rhythm-mix).
*   **Import Mix...** &#x20;

    Notez que cela importera les paramètres uniquement pour les instruments qui sont communs entre le mix courant et le mix importé.

### Menu Edit

*   **Reset channels** &#x20;

    Restaure chaque canal de la mix console (instrument, volume, panoramique, effet) à son paramètre de rhythm par défaut.

### Menu Midi

*   **Enable/Disable all Midi parameters** &#x20;

    Par défaut, tous les paramètres Midi sont activés. \
    Utilisez Disable all Midi parameters si vous souhaitez contrôler le mix vous-même directement sur le output synth : dans ce mode, JJazzLab n'envoie que des _messages de notes Midi_, sans envoyer de messages Midi relatifs aux changements de banque/programme, au volume, au panoramique ou aux effets.
*   **Send GM/GM2/XG/GM mode ON message** &#x20;

    Cela vous permet d'envoyer des messages d'initialisation Midi spéciaux pour mettre votre output synth dans le mode souhaité.

## Changer d'instrument

Cliquez sur le nom de l'instrument dans le canal. Notez que c'est également là que la transposition de l'instrument peut être ajustée.

![](../.gitbook/assets/mixconsole-instrumentselection.png)

## Paramètres de canal

Utilisez les paramètres de canal pour :

*   **Ajouter un décalage de vélocité Midi à toutes les notes jouées sur ce canal** &#x20;

    Notez que c'est légèrement différent du réglage du volume.<br>
*   **Désactiver l'envoi de messages Midi spécifiques** &#x20;

    Probablement parce que vous contrôlez vous-même le paramètre directement sur le [output synth](/broken/pages/-MQNBJUwiJ9pkXF9j5Ey).<br>
*   **Activer un canal de batterie avec un canal Midi différent de 10**

    Si vous utilisez un output synth GM de base, il ne peut jouer la batterie **que sur le canal 10**. Si la batterie/percussion est utilisée sur d'autres canaux dans votre mix, vous devez activer le réacheminement de la batterie sur ces canaux. Notez que JJazzLab peut activer cette option pour vous s'il détecte, en fonction des informations du [output synth](/broken/pages/-MQNBJUwiJ9pkXF9j5Ey) courant, des problèmes potentiels. \
    <br>

![](../.gitbook/assets/mixconsole-channelsettings.png)

## Canal Midi

Chaque canal Midi peut être modifié manuellement, il suffit de cliquer sur le numéro du canal.

![](../.gitbook/assets/MixConsole-ChangeChannel.png)

## User tracks

Un user track vous permet d'ajouter votre propre contenu Midi à votre song : une mélodie, des riffs de cuivres, des percussions, etc.

{% hint style="info" %}
Si vous souhaitez personnaliser une piste de rhythm uniquement pour un song part (par ex. simplifier la phrase de basse du style pour le 2e verse de votre song), vous devez utiliser le [rhythm parameter Custom phrase](song-structure.md#rhythm-parameters).
{% endhint %}

#### Ajouter des user tracks

Cliquez sur le bouton + dans la barre d'outils de la mix console pour ajouter un nouveau user track. Cela ouvrira également le [notes editor](notes-editor.md) pour éditer ce user track.

<figure><img src="../.gitbook/assets/2023-12-31 22_01_24-JJazzLab  4.0.2.png" alt=""><figcaption><p>Bouton Ajouter un user track</p></figcaption></figure>

Vous pouvez également cloner une piste de rhythm comme nouveau user track en utilisant le signe + dans le coin supérieur droit d'une vue d'ensemble de piste, comme indiqué ci-dessous. La piste de rhythm originale sera automatiquement mise en sourdine.

<figure><img src="../.gitbook/assets/2023-12-31 21_58_28-JJazzLab  4.0.2.png" alt=""><figcaption><p>Cloner une piste de rhythm comme nouveau user track</p></figcaption></figure>

{% hint style="warning" %}
Si vous sélectionnez un instrument de batterie ou de percussion pour le user track, _et_ que votre output synth est un synthétiseur basique compatible GM : [définissez le canal du user track](mix-console.md#midi-channel) sur 10, et si le canal 10 est déjà utilisé par une autre piste, activez le _Drums rerouting to channel 10_ (voir [Paramètres de canal](mix-console.md#channel-settings)) dans votre user track.
{% endhint %}

#### Éditer un user track

Éditez le user track en cliquant sur l'icône en haut à gauche du composant de vue d'ensemble du user track, comme indiqué ci-dessous.&#x20;

Cela ouvrira le [notes editor](notes-editor.md).

<figure><img src="../.gitbook/assets/2023-12-31 22_02_16-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

Un user track a toujours la même longueur que votre song.

{% hint style="danger" %}
Si vous éditez un user track, puis raccourcissez le song (par ex. en supprimant un song part), le user track sera tronqué à la nouvelle taille du song.
{% endhint %}

## Exporter vers un fichier Midi avec glisser-déposer

Vous pouvez exporter la **piste d'accompagnement complète** vers un fichier Midi en faisant glisser la souris depuis la zone vide de la mix console. Notez que c'est la même chose que le menu File/Export to Midi file, sauf que c'est plus pratique lorsque vous travaillez avec un autre logiciel tel qu'une DAW.

Pour exporter une **piste individuelle**, commencez le glissement depuis l'icône de piste ou le composant de vue d'ensemble de la piste.

![Export a single track with mouse drag & drop](../.gitbook/assets/MixConsoleDragTrack.png)

## Songs multi-rhythms

Lorsqu'un song utilise 2 rhythms ou plus, un menu contextuel s'affiche dans le coin supérieur gauche de la mix console pour sélectionner le rhythm que vous souhaitez afficher.

![](../.gitbook/assets/mixconsole-rhythmselectionpopup.png)

Notez que certaines commandes telles que le menu **Edit/Reset channels** ne seront pas appliquées au(x) rhythm(s) masqué(s).

## Raccourcis souris

| Sélection                                     | Souris                       | Action                                  |
| --------------------------------------------- | ---------------------------- | --------------------------------------- |
| curseur de volume de canal, potentiomètres    | double-clic                  | saisir la valeur au clavier             |
| curseur de volume de canal                    | shift + glisser la souris    | modifier le volume de tous les canaux   |
