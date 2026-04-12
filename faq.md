---
description: Foire Aux Questions
---

# FAQ

## J'aime JJazzLab, comment puis-je aider ? <a href="#how-to-help" id="how-to-help"></a>

* [**Faites un don**](https://www.jjazzlab.org/en/donate/) pour garder JJazzLab 100% gratuit, sans publicité
* Aidez à [traduire](contribute/translate-jjazzlab.md) JJazzLab (notamment si vous parlez japonais ou coréen)
* [Contribuez](contribute/improve-doc.md) à améliorer cette documentation
* "Likez" les vidéos et abonnez-vous à la [chaîne YouTube](https://www.youtube.com/channel/UC0L3SwjY6bhTj6jsbOYzzAw)
* Enregistrez une vidéo de vous-même en train de jouer avec JJazzLab : les vidéos seront mises sur la chaîne YouTube de JJazzLab
* Faites passer le mot ! Parlez et ajoutez des liens vers **www.jjazzlab.org** sur les réseaux sociaux, les blogs, les sites web, etc.
* Si vous êtes développeur, contribuez au code sur [GitHub](https://github.com/jjazzboss/JJazzLab).

## J'utilise MacOS, je ne trouve pas le menu **Tools/Options ?**

Sous MacOS, les **Options** sont accessibles via le menu principal **JJazzLab/Preferences**.

## Comment transposer un song ? <a href="#how-to-transpose-song" id="how-to-transpose-song"></a>

1. Sélectionnez tous les chord symbols (menu contextuel **Select all the chord symbols**)
2. Utilisez la molette de la souris, ou le menu contextuel **Transpose**

## Puis-je utiliser des plugins VST/AU avec JJazzLab ?

Oui, mais pas directement car JJazzLab ne peut pas héberger de plugins VST.&#x20;

1. Installez un périphérique midi virtuel et un logiciel hôte VST sur votre ordinateur. Vous trouverez sur le web des applications gratuites pour Windows, Linux et Mac. Par exemple, utilisez **loopMIDI** (nous recommandons de désactiver sa _détection de retour_ dans les paramètres _Avancé_) et **SoundBridge** sous Windows.
2. Dans JJazzLab, allez dans **options Midi** et réglez le **périphérique Midi out** sur **loopMIDI**
3. Dans votre logiciel VST Host, réglez le **périphérique Midi in** sur **loopMidi** et assurez-vous que l'hôte VST et les plugins VST sont configurés de sorte que tous les canaux Midi (1-16) soient reçus.
4. Jouez un song dans JJazzLab : vous devriez entendre les instruments VST
5. Si vous ne souhaitez pas sélectionner les sons VST directement depuis JJazzLab, vous pouvez _Désactiver tous les paramètres Midi_ via le menu Midi dans le mix console.

## Comment générer un fichier audio (.mp3, .wav, etc.) depuis un backing track JJazzLab ? <a href="#generate-mp3" id="generate-mp3"></a>

Depuis JJazzLab 4, utilisez simplement le **menu File/Export to audio** - cela nécessite que FluidSynth soit le output synth. Si vous sélectionnez l'option "Separate tracks", un fichier audio sera généré par piste.&#x20;

## Comment forcer une réinstallation propre ?

Vous devez réinitialiser tous les paramètres utilisateur JJazzLab (désinstaller/réinstaller ne suffit pas).

La méthode simple : menu **Tools/Options/Advanced,** bouton **Reset all user settings**.

La méthode manuelle : trouvez l'emplacement de votre **Netbeans user dir** dans le menu **Help/About/System Information**, quittez JJazzLab puis supprimez le **Netbeans user dir**.

## Je n'ai pas de droits d'administrateur sur mon ordinateur Windows, puis-je installer JJazzLab ?

Oui. Lorsque le programme d'installation JJazzLab vous le demande pour la première fois, sélectionnez "Install only for me", puis choisissez un répertoire d'installation où vous avez les droits en écriture (dans Mes Documents par exemple).

## Comment obtenir de meilleurs sons ?

Depuis JJazzLab 4, l'application intègre un synthétiseur logiciel prêt à l'emploi (FluidSynth) configuré de manière optimale pour JJazzLab, avec des sons corrects.

Pour obtenir de meilleurs sons, vous devrez connecter JJazzLab à un synthétiseur matériel ou à des [plugins VST/AU](faq.md#puis-je-utiliser-des-plugins-vst-au-avec-jjazzlab) via Midi.

{% hint style="success" %}
Il existe une version gratuite de Halion Sonic SE de Steinberg qui peut être utilisée avec JJazzLab pour obtenir des backing tracks avec un **son vraiment excellent**, plus d'informations sur le [forum JJazzLab](https://jjazzlab.freeforums.net/thread/215/new-great-sounds-jjazzlab).
{% endhint %}

## J'ai un clavier arrangeur Yamaha (Tyros, PSR, ...), comment l'utiliser avec JJazzLab ?

JJazzLab peut piloter votre clavier pour bénéficier de ses sons optimisés.&#x20;

* Connectez votre clavier via Midi
* Allez dans l'onglet Midi Out de Options/Preferences
* Sélectionnez la sortie Midi connectée à votre synthétiseur
* Dans la section Output Synth, sélectionnez **Add synth from file..** et choisissez **YamahaRefSynth.ins**.

## Comment agrandir les polices ? <a href="#font-bigger" id="font-bigger"></a>

Dans le répertoire d'installation de JJazzLab, éditez le fichier **etc/jjazzlab.conf** et ajoutez **--fontsize 16** (16 ou toute autre valeur, la valeur par défaut est 11) dans la variable **default\_options**, vous devriez obtenir quelque chose comme ceci :

`default_options="--branding jjazzlab -J-Djjazzlab.version=2.2.0 -J-Dplugin.manager.check.new.plugins=true -J-Dplugin.manager.check.interval=EVERY_DAY --fontsize 16"`

Redémarrez JJazzLab. Tous les menus devraient apparaître plus grands.

Cela ne résoudra pas tout, car certaines polices des éditeurs ne dépendent pas de ce paramètre. Mais vous pouvez en modifier certaines via le menu **Tools/Options/Theme**. Vérifiez chaque élément de la liste et si une police est définie, modifiez-la pour l'agrandir. Les paramètres utilisateur sont automatiquement enregistrés, vous ne devez donc le faire qu'une seule fois.

{% hint style="info" %}
Si vous utilisez des moniteurs 4K ou 5K, JJazzLab peut sembler trop petit, avec des polices illisibles. Dans ce cas, ajoutez **-J-Dsun.java2d.uiScale=2** dans la variable **default\_options**, comme dans l'exemple ci-dessus. JJazzLab apparaîtra deux fois plus grand.
{% endhint %}

## Puis-je démarrer JJazzLab avec des arguments de ligne de commande ?

Vous pouvez passer un ou plusieurs noms de fichiers .sng sur la ligne de commande, JJazzLab les ouvrira au démarrage.

```
# Example on Win10 (x64)
"C:\Program Files\JJazzLab\bin\jjazzlab64.exe" "C:\my dir\MySong.sng" "D:\AnotherSong.sng"
```

## Comment soumettre un bug ? Comment trouver le fichier "log" ?

Créez un nouveau fil de discussion dans le [forum JJazzLab](https://jjazzlab.freeforums.net/) ou, si vous êtes un utilisateur GitHub, créez un [sujet](https://github.com/jjazzboss/JJazzLab-X/issues).

Nous avons besoin des informations suivantes pour vous aider :

* Fournir le contenu du **fichier journal** (log file)&#x20;
* Décrire ce qui ne fonctionne pas comme prévu
* Décrire la séquence d'actions à l'origine du problème

{% hint style="info" %}
Un nouveau **fichier journal** est créé à chaque démarrage de JJazzLab. Il est important d'obtenir le bon fichier journal lorsque le problème s'est produit.
{% endhint %}

Pour obtenir le contenu du fichier journal :

1. Après que le problème se soit produit, allez dans le menu **Tools/Options/Advanced**
2. Cliquez sur **Show Log Window**
3. Copiez et collez **le contenu complet** de cette fenêtre dans votre rapport de bug

Si pour une raison quelconque ce qui précède ne fonctionne pas :

1. Allez dans le menu **Help/About** et trouvez l'emplacement de votre **Netbeans user dir**. Par ex. sous Windows `C:\Users\MyName\AppData\Roaming\jjazzlab\2.2` Par ex. sous Linux `/home/MyName/.jjazzlab/2.2`
2. Ouvrez un explorateur, allez dans ce répertoire puis dans le sous-répertoire **var/log**
3. Le dernier fichier journal est **messages.log**, le précédent est **messages.log.1**, celui d'avant est **messages.log.2**, etc.
4. Trouvez le fichier journal approprié et envoyez-le avec votre rapport de bug

{% hint style="danger" %}
Si vous ne trouvez pas le **Netbeans user dir**, assurez-vous que votre explorateur affiche les fichiers cachés (par exemple, le répertoire AppData est généralement caché sous Windows)
{% endhint %}
