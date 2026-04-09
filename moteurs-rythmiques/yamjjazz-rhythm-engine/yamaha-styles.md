# Styles Yamaha

Le moteur [YamJJazz ](./)est capable de lire tous les fichiers de style Yamaha (.sty, .prs, .bcs, .sst, au format SFF1 ou SFF2). Vous pouvez trouver des fichiers de style sur le Web, la plupart d’entre eux gratuitement. Visit la page des [ressources](https://www.jjazzlab.com/en/resources) pour trouver des liens utiles.

Les styles Yamaha ont généralement 4 variations _Main A, Main B, Main_ _C, Main D_, plus quelques _intros_ et _fins_. Chaque variante peut utiliser des pistes des types suivants:

* **Rythme** (ex. batterie)
* **Sous-rythme** (ex percussion)
* **Basse**
* **Accord1** (ex. guitaer)
* **Accord2** (ex. clavier)
* **Pad** (ex violons)
* **Phrase1** (ex. Cuivres)
* **Phrase2**

## Yamaha "Mega Voices”, “Voix Super Articulation ”, ... <a href="#yamaha-specific-voices-mega-voices-super-articulation-voices" id="yamaha-specific-voices-mega-voices-super-articulation-voices"></a>

Les fichiers de style Yamaha sont optimisés pour les claviers arrangeurs Yamaha. Les derniers modèles (Tyros, Genos...) ont de nombreuses voix avec des caractéristiques spéciales (par exemple " Mega Voices "), en particulier pour les guitares qui sont optimisées pour le rendu de style.

Les autres claviers ou SoundFonts (y compris le JJazzLab SoundFont) ne peuvent pas reproduire ces voix spéciales correctement. C’est pourquoi certains fichiers de style Yamaha récents (format SFF2) peuvent ne pas sonner correctement avec JJazzLab. Si cela se produit, localisez les canaux défectueux à l’aide du bouton Solo de la Console de Mixage et baissez leur volume ou coupez-les.

## Limitations <a href="#limitations" id="limitations"></a>

JJazzLab est conçu pour héberger tout type de moteurs de génération rythmique, et ils doivent fonctionner avec n’importe quel type de synthé de sortie, pas seulement les claviers Yamaha. Par conséquent, certaines fonctionnalités spécifiques du fichier de style Yamaha ne sont pas prises en charge:

* Messages Midi SysEx : ignorés.
* Messages du contrôleur : ignorés.
* Sons par variation : ignorés, YamJJazz utilise les sons par défaut du style pour toutes les variations.
* Yamaha Mega Voices : les notes non musicales ou les effets sonores (notes au-dessus de C6) sont ignorés.
* Messages Midi Pitch bend : ignorés.
* Sections OTS et MDB : ignorées.
