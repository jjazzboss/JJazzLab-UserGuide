# Styles Yamaha

Le moteur [YamJJazz](./) est capable de lire tous les fichiers de style Yamaha (.sty, .prs, .bcs, .sst, aux formats SFF1 ou SFF2). Vous pouvez trouver des fichiers de style sur le Web, la plupart d'entre eux gratuitement. Visitez la page des [ressources](https://www.jjazzlab.com/en/resources) pour des liens utiles.

Les styles Yamaha ont généralement 4 variations _Main A, Main B, Main C, Main D_, plus quelques _Intros_ et _Endings_.&#x20;

La plupart du temps, les variations ont l'organisation suivante :

* _Intro A_ : intro d'une mesure, batterie uniquement
* _Intro B_ : intro de 2 mesures avec une séquence d'accords fixe (c.-à-d. que votre intro ne doit contenir qu'un seul accord initial pour définir la tonalité)
* _Intro C_ : identique à B mais avec 4 mesures
* _Main A-D_ : les 4 variations principales du style, du plus léger au plus chargé
* _Ending A_ : fin d'une mesure avec un accord final sur le 1er temps
* _Ending B_ : fin de 2 mesures avec une séquence d'accords fixe (c.-à-d. que votre fin ne doit contenir qu'un seul accord initial pour définir la tonalité)
* _Ending C_ : identique à B mais avec 4 mesures

Vous trouverez également des variations _Fill In AA_, _Fill In BB, Fill In CC, Fill In DD, Fill In BA_, qui correspondent à des transitions d'une mesure, généralement avec un fill ou un break de batterie. Vous n'avez normalement pas à les utiliser directement car JJazzLab le fait automatiquement à la fin de chaque section, en fonction de la valeur du **rhythm parameter** Fill de la batterie.

Chaque variation peut utiliser des pistes des types suivants :

* **Rhythm** (ex. batterie)
* **Sub-rhythm** (ex. percussions)
* **Bass**
* **Chord1** (ex. guitare)
* **Chord2** (ex. clavier)
* **Pad** (ex. cordes)
* **Phrase1** (ex. cuivres)
* **Phrase2**

## Yamaha « Mega Voices », « Super Articulation Voices », … <a href="#yamaha-specific-voices-mega-voices-super-articulation-voices" id="yamaha-specific-voices-mega-voices-super-articulation-voices"></a>

Les fichiers de style Yamaha sont optimisés pour les claviers arrangeurs Yamaha. Les derniers modèles (Tyros, Genos…) disposent de nombreuses voix avec des caractéristiques spéciales (ex. « Mega Voices »), notamment pour les guitares qui sont optimisées pour le rendu des styles.

Les autres claviers ou synthés ne peuvent pas reproduire ces voix spéciales correctement. C'est pourquoi certains fichiers de style Yamaha récents (format SFF2) peuvent ne pas sonner correctement avec JJazzLab. Si cela se produit, localisez les canaux défectueux à l'aide du bouton Solo dans le mix console, et baissez leur volume ou coupez-les.

## Limitations <a href="#limitations" id="limitations"></a>

JJazzLab est conçu pour héberger tout type de rhythm engines, et ils doivent fonctionner avec n'importe quel type d'output synth, pas seulement les claviers Yamaha. Par conséquent, certaines fonctionnalités spécifiques des fichiers de style Yamaha ne sont pas prises en charge :

* Messages Midi SysEx : ignorés.
* Messages de contrôleur : ignorés.
* Sons par variation : ignorés, YamJJazz utilise les sons par défaut du style pour toutes les variations.
* Yamaha Mega Voices : les notes non musicales ou les effets sonores (notes au-dessus de C6) sont ignorés.
* Messages Midi Pitch bend : ignorés.
* Sections OTS et MDB : ignorées.
