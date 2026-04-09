# JJazzLab

{% hint style="danger" %}
!! **La documentation en français n'est plus à jour par rapport à la dernière version JJazzLab 5 !!**

**La documentation de référence est celle en ANGLAIS: le mieux est de demander à votre IA (Mistral, ChatGPT, etc.) de traduire les pages qui vous intéressent en français.**


{% endhint %}

{% hint style="info" %}
Vous souhaitez ajouter ou corriger de la documentation ? Oui, vous pouvez !😀 Visitez la page Améliorer la documentation( [Improve documentation](contribuer/improve-doc.md)).
{% endhint %}

![JJazzlab 3](<.gitbook/assets/JJazzLab3.0Full (1).png>)

## Par où commencer ?

Regarder cette courte vidéo [video tutorial](video-tutorials.md#for-starters).

## Qu'est-ce que JjazzLab ?

🎵 JJazzLab est une application de bureau qui génère automatiquement des pistes d’accompagnement pour n’importe quel morceau, même les plus complexes. C’est un compagnon de jam pour s’amuser à improviser à la maison, apprendre de nouvelles choses ou simplement pratiquer votre instrument. C’est aussi un excellent outil pour les enseignants.

🎷 JJazzLab est conçu pour créer des pistes d’accompagnement non ennuyeuses, des pistes d’accompagnement avec de la variété, des accents rythmiques et dynamiques. Vous pouvez commencer un solo lentement et construire progressivement votre morceau !

💻 JJazzLab est open-source, les développeurs peuvent facilement ajouter de nouvelles fonctionnalités et de nouvelles capacités de génération de musique.

## Fonctionnalités

### Pistes d'accompagnement

* Génération instantanée d’une piste d’accompagnement Midi avec batterie, percussions, basse, piano, guitare, pad, section de cuivres, ...
* Réglage fin de la piste d’accompagnement par partie de morceau : variation rythmique, intensité, instruments en sourdine, fill de batterie, facteur de tempo, phrases personnalisées, transformation de batterie...
* Jouez de n’importe ou, bouclez les mesures sélectionnées
* Jeu transposé (par exemple pour saxophonistes ou trompettistes)
* Toute structure de morceau : intro, refrain, 1ère coda, etc.
* Ajuster le tempo, la transposition, choisissez les instruments solo/mute
* Importer des pistes utilisateur
* Prise en charge des pistes d’accompagnement multi-rythme, éventuellement avec des signatures temporelles différentes.
* Exporter vers un fichier Midi, la piste d’accompagnement complète ou une piste d’instrument unique
* Conversion Midi en MP3 facile via l’exportation vers un fichier
* Midi Clic et décomptage personnalisables

### Editeurs

* Éditeur de partition d’accords, éditeur de structure de morceau, éditeur de symboles d’accords, console de mixage, éditeur de mémo de morceau
* Éditeur multi-fichiers avec fenêtres ancrables
* Interface utilisateur intuitive avec annulation / rétablissement, copier/coller entre les morceaux.
* Placement libre des symboles d’accords (quantifiés ou non), anticipation des symboles d’accords décalés
* Prise en charge de tous les symboles d’accords pop-rock et jazz, ainsi que des symboles d’accords définis par l’utilisateur.
* Modifier le rendu musical des symboles d’accord : harmonie sous-jacente, type d’accent, variation d’harmonie pendant les solos, substitution du symbole d’accord, ...
* Prise en charge du glisser-déposer pour importer / exporter des fichiers Midi
* Modèle de morceau personnalisable
* Couleurs et polices de l’interface utilisateur personnalisables
* Imprimer la feuille d’accord et la structure du morceau

### Rhythmes

* Prise en charge des fichiers de style Yamaha (formats SFF1 et SFF2), accès à des milliers de styles gratuits sur le Web
* Des centaines de rythmes intégrés dans le programme d’installation
* Prise en charge des fichiers de style « YamJJazz Extended Yamaha » pour encore plus de variations par style.
* Architecture ouverte : de nouveaux moteurs de génération rythmique peuvent être facilement ajoutés via des plugins.

### Visionneuse de notes

* Afficher les notes de piste d’accompagnement en temps réel
* Afficher les notes et gammes du symbole d’accord sélectionné
* Clavier de piano
* Diagrammes de guitare avec les accords les plus courants, accords vocaux ouverts / fermés, inversions

### (pseudo) Mode clavier arrangeur

* Reconnaître les accords joués sur Midi IN et mettre à jour la piste d’accompagnement en (pseudo) temps réel

### Aide à l'improvisation

* Générer automatiquement des guides d’improvisation sur votre feuille d’accord&#x20;
* Basé sur le livre de référence de Hal Crook " Comment improviser "

### Midi

* ![](file:///C:/Users/beran/AppData/Local/Temp/msohtmlclip1/01/clip_image001.gif)Connectez-vous à n’importe quel moteur audio via Midi : lecteur SoundFont (recommandé avec le JJazzLab SoundFont), synthé interne Java, synthé externe, hôte VST via port Midi virtuel tel que 'LoopBe1'
* Compatible avec les instruments GM/GM2/XG/GS
* Compatible avec n’importe quel instrument Midi via les fichiers de définition d’instruments Cakewalk (.ins)
* Remappage automatique de la batterie / percussion, des touches Yamaha XG, des touches GM/GM2/GS
* SoundFont JJazzLab optimisé pour un rendu de haute qualité et une sélection automatique des instruments
* Préréglages prêts à l’emploi pour VirtualMidiSynth (Windows) et FluidSynth (Linux)
* Mixage par défaut par rythme défini par l’utilisateur
* Instruments par défaut définis par l’utilisateur

### Importation

* Fichiers de partition Band-In-A-Box
* Fichiers musicXML
* XML Impro-Visor

### **Diver**s

* Mémo de morceau avec des liens hypertexte ouverts lors du chargement du morceau
* Ajoutez facilement de nouvelles fonctionnalités grâce à l’architecture ouverte open-source
* Basé sur le framework d’application Netbeans
