# Vue d'ensemble des rhythm engines

Les **rhythms** sont rendus disponibles par des **rhythm engines**.

Grâce à son architecture open-source et enfichable, JJazzLab peut héberger de nombreux rhythm engines différents. Si vous êtes un développeur, vous pouvez construire le vôtre assez facilement !

![](../.gitbook/assets/rhythmpluginsarchitecture.png)

Un rhythm engine a **un ou plusieurs fournisseurs de rhythms** qui proposent une liste des rhythms pris en charge et les **rhythm parameters** supportés. Vous pouvez voir la liste de tous les **fournisseurs de rhythms** disponibles dans la **boîte de dialogue de sélection du rhythm**.

![](../.gitbook/assets/rhythmgenerationengine.png)

JJazzLab comprend actuellement un rhythm engine, [YamJJazz](yamjjazz-rhythm-engine/), basé sur les styles Yamaha. Ses **rhythm parameters** sont Variation, Intensity et Fill (d'autres paramètres tels que Mute ou Tempo Factor sont génériques et fonctionnent avec n'importe quel rhythm).

## Futurs rhythm engines <a href="#future-rhythm-generation-engines" id="future-rhythm-generation-engines"></a>

Voici quelques exemples de ce qui pourrait être développé en utilisant l'infrastructure JJazzLab-X.

* Un moteur orienté jazz basé sur l'IA avec un seul rhythm polyvalent qui s'adapte à différents contextes, comme un vrai groupe (tempo lent ou rapide, walking bass ou non, etc.).
* Un moteur de batterie similaire au batteur virtuel Logic Pro X
* Un moteur capable d'adapter la piste d'accompagnement à une mélodie donnée
* Un « méta-moteur » qui permet de combiner des pistes individuelles de différents rhythms (par exemple, combiner une ligne de basse hip-hop avec une batterie latine)
* Un moteur capable de lire les fichiers de style de Band-In-A-Box ou d'autres claviers arrangeurs tels que Korg ou Ketron
* etc.
