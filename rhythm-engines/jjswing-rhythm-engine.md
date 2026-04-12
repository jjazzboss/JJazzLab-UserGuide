---
description: Le style ultime pour pratiquer les standards de jazz avec un feeling naturel
---

# jjSwing rhythm engine

Les caractéristiques uniques de **jjSwing** sont :

* Une **walking bass réaliste avec des lignes mélodiques**
* Le feeling swing s'ajuste automatiquement au tempo
* 11 variations de batterie (brosses, hi-hat, ride, shuffle)
* Capacité double-time (jouer deux fois plus vite avec des changements d'accords au tempo original)
* La possibilité d'ajuster la basse et la batterie indépendamment

{% hint style="danger" %}
jjSwing est optimisé pour fonctionner avec le [FluidSynth](../sounds/using-fluidsynth.md) interne comme output synth. Si vous utilisez un output synth différent, vous pourriez entendre des sons étranges.
{% endhint %}

Notez que la version actuelle de jjSwing ne supporte que la signature rythmique 4/4. Le support de la valse jazz sera ajouté ultérieurement.

{% embed url="https://www.youtube.com/watch?v=NZ3VC5GcdiA" %}

## Rhythm parameters

jjSwing a 2 rhythm parameters spécifiques : bass style et drums style.

### Bass style

Les valeurs possibles sont indiquées dans l'image ci-dessous.

<figure><img src="../.gitbook/assets/jjSwing-bassStyle.png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="135">Bass style</th><th>Description</th></tr></thead><tbody><tr><td>auto</td><td>Le bass style effectif dépend de la variation du rhythm (ex. Main A-1)</td></tr><tr><td>2-feel</td><td>Walking en deux</td></tr><tr><td>walking</td><td>Walking bass</td></tr><tr><td>double-note</td><td>Walking bass avec de nombreuses doubles notes (notes répétées)</td></tr><tr><td>double-time</td><td>Walking bass jouée deux fois plus vite tout en préservant les changements d'accords au tempo original. À utiliser lorsque le Drums style est également réglé sur double-time.</td></tr><tr><td>intro</td><td>À utiliser avec la variation de rhythm Intro A</td></tr><tr><td>ending</td><td>À utiliser avec la variation de rhythm Ending A</td></tr><tr><td></td><td></td></tr></tbody></table>

### Drums style

Les valeurs possibles sont indiquées dans l'image ci-dessous.

<figure><img src="../.gitbook/assets/jjSwing-drumsStyle.png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="135">Drums style</th><th>Description</th></tr></thead><tbody><tr><td>auto</td><td>Le drums style effectif dépend de la variation du rhythm (ex. Main A-1)</td></tr><tr><td>brushes 1/2</td><td>2 styles de batterie différents aux brosses</td></tr><tr><td>hi-hat 1/2</td><td>2 styles de batterie différents au hi-hat</td></tr><tr><td>ride 1/2/3/4</td><td>4 styles de batterie différents à la cymbale ride</td></tr><tr><td>shuffle 1/2</td><td>2 styles de batterie différents en 12/8</td></tr><tr><td>double</td><td>Batterie jouée deux fois plus vite tout en préservant les changements d'accords au tempo original. À utiliser lorsque le Bass style est également réglé sur double-time.</td></tr><tr><td>intro</td><td>À utiliser avec la variation de rhythm Intro A</td></tr><tr><td>ending</td><td>À utiliser avec la variation de rhythm Ending A</td></tr></tbody></table>

## Settings

Les settings de jjSwing sont disponibles dans l'onglet Options/Rhythms ou dans la boîte de dialogue de sélection du rhythm, lorsque vous sélectionnez le fournisseur de rhythm **jjSwing styles**, comme indiqué ci-dessous.

<figure><img src="../.gitbook/assets/jjSwing-SettingsButton.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/jjSwing-SettingsWindow.png" alt=""><figcaption></figcaption></figure>
