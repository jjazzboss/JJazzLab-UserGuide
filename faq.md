---
description: Foire Aux Questions
---

# FAQ

## J'aime JJazzLab et je veux le garder gratuit, comment puis-je aider ? <a href="#how-to-help" id="how-to-help"></a>

* [Faites un don pour que JJazzLab ](https://www.jjazzlab.com/en/donate/)reste gratuit pour tous
* [Aidez à traduire](contribuer/translate-jjazzlab/) JJazzLab
* [Contribuez](contribuer/improve-doc.md) à l’amélioration de cette documentation
* "Likez" les videos et abonnez vous à la [chaîne YouTube](https://www.youtube.com/channel/UC0L3SwjY6bhTj6jsbOYzzAw)
* Enregistrez une vidéo de vous-même en train de jouer avec JJazzLab : les vidéos seront mises sur la chaîne YouTube de JJazzLab
* Faites passer le mot ! Parlez et ajoutez des liens vers [www.jjazzlab.com ](http://www.jjazzlab.com/)sur les réseaux sociaux, les blogs, les sites Web, etc.
* Si vous êtes un développeur,[contribuez au code](https://github.com/jjazzboss/JJazzLab-X/blob/master/CONTRIBUTING.md)

## J’utilise MacOS, je ne trouve pas le menu Outils/Options **?**

Sous MacOS, **les options** sont accessibles via le menu principal **JJazzLab/Préférences**.

## Comment transposer un morceau ? <a href="#how-to-transpose-song" id="how-to-transpose-song"></a>

1. Sélectionnez tous les symboles d’accord (menu contextuel **Sélectionnez tous les symboles d’accord**)
2. Utilisez la molette de la souris ou cliquez avec le bouton droit sur le menu **Transposer**

## Puis-je utiliser des plugins VST/AU avec JJazzLab ?

Oui, mais pas directement car JJazzLab ne peut pas héberger de plugins VST.

1. Installez un périphérique midi virtuel et un logiciel hôte VST sur votre ordinateur. Vous trouverez sur le web des applications gratuites pour Windows, Linux et Mac. Par exemple, utilisez **loopMIDI** (nous vous recommandons de désactiver sa détection de retour dans les paramètres avancés) et **SoundBridge** sous Windows.
2. DansJJazzLab, allez dans **options Midi** et définissez le périphérique de sortie **Midi** sur **loopMIDI**
3. Dans votre logiciel VST Host, réglez le périphérique Midi in sur loopMidi et assurez-vous que l’hôte VST et les plugins VST sont configurés de sorte que tous les canaux Midi (1-16) soient reçus.
4. Jouez un morceau dans JJazzLab : vous devriez entendre les instruments VST

## Comment forcer une réinstallation propre ?

Vous devez réinitialiser tous les paramètres utilisateur JJazzLab (désinstaller/réinstaller ne suffit pas).

La méthode simple : menu **Outils/Options/Avancé,** bouton **Réinitialiser tous les paramètres utilisateur.**

La méthode dure : trouvez l’emplacement de votre **répertoire utilisateur Netbeans** dans le menu **Aide/À propos/Informations système**, quittez **JJazzLab,** puis \*\* **le répertoire utilisateur Netbeans\*\***.

## Je n'ai pas de droit administrateur sur mon ordinateur Windows, puis-je installer JJazzLab ?



## Comment agrandir les polices ? <a href="#font-bigger" id="font-bigger"></a>

Dans le répertoire d’installation de JJazzLab, éditez le fichier **etc/jjazzlab.conf** et ajoutez **--fontsize 16** (16 ou toute autre valeur, la valeur par défaut est 11) dans la variable default\_options, vous devriez vous retrouver avec quelque chose comme ceci :

`default_options="--branding jjazzlab -J-Djjazzlab.version=2.2.0 -J-Dplugin.manager.check.new.plugins=true -J-Dplugin.manager.check.interval=EVERY_DAY --fontsize 16"`

Redémarrez JJazzLab. Tous les menus ont l'air plus grands maintenant.

Cela ne résoudra pas tout, car certaines polices d’éditeur ne dépendent pas de ce paramètre. Mais vous pouvez modifier certains d’entre eux en utilisant le menu **Outils / Options / Thème**. Vérifiez chaque élément de la liste et si une police est définie, modifiez-la pour l’agrandir. Les paramètres utilisateur sont automatiquement enregistrés, vous ne devez donc le faire qu’une seule fois.

{% hint style="info" %}
Si vous utilisez des moniteurs 4K ou 5K, JJazzLab peut sembler trop petit, avec des polices illisibles. Dans ce cas, ajoutez **-J-Dsun.java2d.uiScale=2** dans la variable **default\_options**, comme dans l’exemple ci-dessus. JJazzLab aura l’air deux fois plus grand.
{% endhint %}

## Puis-je démarrer JJazzLab avec des arguments de ligne de commande ?

YVous pouvez passer un ou plusieurs noms de fichiers. sng sur la ligne de commande, JJazzLab les ouvrira au démarrage.

```
# Example on Win10 (x64)
"C:\Program Files\JJazzLab\bin\jjazzlab64.exe" "C:\my dir\MySong.sng" "D:\AnotherSong.sng"
```

## Comment soumettre un bug ? Comment trouver le fichier "log" ?

Créez un nouveau fil de discussion dans le [forum JJazzLab ](https://jjazzlab.freeforums.net/)ou, si vous êtes un utilisateur GitHub, créez un [sujet](https://github.com/jjazzboss/JJazzLab-X/issues).

Nous avons besoin des informations suivantes pour vous aider:

* Fournir le contenu du fichier journal (**fichier log**)&#x20;
* Décrire ce qui ne fonctionne pas comme prévu
* Décrire la séquence d’actions à l’origine du problème

{% hint style="info" %}
Un nouveau **fichier journal** **(log)** est créé à chaque démarrage de JJazzLab. Il est important d’obtenir le bon fichier journal lorsque le problème s’est produit.
{% endhint %}

Pour obtenir le contenu du fichier journal :

1. Juste après que le problème se soit produit, allez dans le menu **Outils / Options / Avancé**
2. Cliquez sur **Afficher la fenêtre du journal**
3. Copiez et collez le **contenu complet** de cette fenêtre dans votre rapport de bug.

Si, pour une raison quelconque, ce qui précède ne fonctionne pas :

1.  Allez dans le menu **Aide/À propos** et trouvez l’emplacement de votre **répertoire utilisateur Netbeans**. Par ex. sous Windows

    &#x20;`C:\Users\MyName\AppData\Roaming\jjazzlab\2.2` For ex. on Linux `/home/MyName/.jjazzlab/2.2`
2. Ouvrez l'explorateur, aller dans ce répertoire et ensuitedans le sous-répertoire **var/log**
3. Le dernier fichier journal est **messages.log**, le précédent est **messages.log.1**, celui d'avant est **messages.log.2**, etc.
4. Trouvez le fichier journal approprié et envoyez-le avec votre rapport de bug.

{% hint style="danger" %}
Si vous ne trouvez pas le répertoire **Netbeans user dir**., assurez-vous que votre explorateur affiche les dossiers cachés (par exemple le répertoire AppData est généralement caché sous usually Windows)
{% endhint %}
