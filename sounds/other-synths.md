---
description: Connecter JJazzLab à d'autres synthétiseurs via Midi.
---

# Other synths

En général, nous recommandons d'utiliser [FluidSynth](using-fluidsynth.md) : aucune configuration requise et des sons corrects.&#x20;

Mais si vous disposez d'un synthétiseur matériel ou logiciel de haute qualité (VST, AU, AAX, ...), vous pouvez l'utiliser avec JJazzLab via un câble Midi ou un câble/dispositif Midi virtuel (tel que LoopMIDI pour Windows).

![Connecting a Midi synth to JJazzLab](<../.gitbook/assets/MidiWizard-image1 (1).png>)

Dans l'onglet **Midi** des **Options/Preferences :**

* Décochez "use FluidSynth"
* Sélectionnez un périphérique Midi OUT
* Sélectionnez un Output Synth qui décrit les capacités du synthétiseur connecté.&#x20;

Les informations de l'**Output Synth** permettent à JJazzLab d'afficher et de sélectionner directement les sounds/instruments du synthétiseur depuis le mix console. Ces informations sont également utilisées pour remapper les notes de batterie si nécessaire (les styles Yamaha utilisent des drum maps XG, mais votre synthétiseur ne le fait peut-être pas).

{% hint style="danger" %}
Si vous entendez de mauvais instruments (par exemple des notes de piano à la place de notes de basse, etc.), ou si vous ne pouvez pas sélectionner des instruments depuis le [mix console](../editors/mix-console.md), cela signifie généralement que les informations de votre **Output Synth** ne correspondent pas à votre synthétiseur connecté. Par exemple, vous avez connecté un synthétiseur non-GM mais l'**Output Synth** est réglé sur GM Synth.
{% endhint %}

Il existe une liste prédéfinie d'Output Synths comme indiqué ci-dessous. Si votre synthétiseur a des capacités supplémentaires, vous pouvez utiliser "**Add a synth from file...**" pour charger un fichier de définition de synthétiseur Midi (.ins). Voir ci-dessous pour plus d'informations sur le format .ins.

<figure><img src="../.gitbook/assets/2023-12-31 18_23_58-Options.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Lorsque vous utilisez un synthétiseur logiciel (par ex. un plugin VST), vous préférerez peut-être contrôler la sélection des sons et les réglages du mix (volume, effets, etc.) directement depuis l'interface du plugin VST. Dans ce cas, vous devriez [Désactiver tous les paramètres Midi](../editors/mix-console.md#menu-midi) depuis le mix console de JJazzLab, afin que JJazzLab n'envoie que des notes Midi.
{% endhint %}

## Midi synth definition files (.ins)

JJazzLab peut lire les **fichiers de définition d'instruments Cakewalk** (.ins). Ces fichiers sont utilisés par de nombreux DAW ; recherchez sur le web pour plus d'informations sur le format .ins.

Un fichier **.ins** définit un **Midi synth** avec sa liste d'instruments et la façon de les sélectionner via Midi (valeurs Bank Select/Program Change).

### JJazzLab .ins format extensions <a href="#jjazzlab-ins-format-extensions" id="jjazzlab-ins-format-extensions"></a>

{% hint style="info" %}
Ces extensions du format .ins ne sont pas obligatoires pour que JJazzLab fonctionne. Mais elles sont nécessaires si vous disposez d'un fichier .ins personnalisé et souhaitez bénéficier pleinement des fonctionnalités de JJazzLab pour obtenir de meilleures pistes d'accompagnement.
{% endhint %}

Le format de fichier .ins standard manque de certaines informations pour que JJazzLab puisse optimiser pleinement la sélection des instruments et la conversion de la **drum map**.

Pour une utilisation optimale, JJazzLab a besoin :

1. Pour les instruments mélodiques : son instrument **GM substitute**\
   &#x20;Exemple : le **GM substitute** de l'instrument XG '12 String Guitar' est l'instrument GM 'Steel Guitar'
2. Pour les instruments de percussion/kits de batterie : son **type** et sa **drum key map**

C'est pourquoi des extensions de mots-clés (optionnelles) ont été introduites, « \{{ xxxx \}} », comme illustré dans les exemples ci-dessous.

```
;
; {{ SubGM1= }}
;
[PRE1]
0=Pn:Full Concert Grand {{ SubGM1=0 }}       ; substitute = GM Acoustic Piano
1=Pn:Rock Grand Piano   {{ SubGM1=1 }}       ; substitute = GM Bright Piano 
2=Pn:Mellow Grand Piano {{ SubGM1=0 }}       ; substitute = GM Acoustic Piano
5=Pn:Aggressive Grand   {{ SubGM1=1 }}       ; substitute = GM Bright Piano
...
18=Pn:CP 1979           {{ SubGM1=3 }}       ; substitute = GM Electric Grand Piano
19=Pn:CP70 Chorus       {{ SubGM1=3 }}       ; substitute = GM Piano
...
```

```
;
; {{ DrumKit= type, keymap }}
;   type=STANDARD, POWER, ROOM, ELECTRONIC, ANALOG, JAZZ, BRUSH, ORCHESTRA, SFX
;   keymap=GM, GS_GM2, XG
;
[DR:PRE]
0=Dr:Power Standard Kit 1   {{DrumKit=POWER, XG}} 
1=Dr:Power Standard Kit 2   {{DrumKit=POWER, XG}} 
2=Dr:Hyper Standard Kit     {{DrumKit=STANDARD, XG}} 
3=Dr:Dry Standard Kit       {{DrumKit=ROOM, XG}} 
...
```

Il existe également 2 extensions de mots-clés spéciales si votre synthétiseur est compatible GS :

```
; For GS-compatible synths only
; {{ UseGsInstruments }}       => For melodic instrument selection a GS Sysex message will be sent to make sure channel is in melodic mode
; {{ UseGsDrumsInstruments }}  => For drums instrument selection a GS Sysex message will be sent to make sure channel is in percussion mode
;
[JJazzLab SoundFont (GS)]
BankSelMethod=1                                ; Use Bank Select MSB only
Patch[0]=GM Bank  {{ UseGsInstruments }}       ; This bank stores GS melodic instruments
Patch[128]=Bank 1 {{ UseGsInstruments }}       ; This bank stores GS melodic instruments 
Patch[256]=Bank 2 {{ UseGsInstruments }}       ; This bank stores GS melodic instruments
...
Patch[*]=Drums    {{ UseGsDrumsInstruments }}  ; This bank stores GS drums instruments
...
```
