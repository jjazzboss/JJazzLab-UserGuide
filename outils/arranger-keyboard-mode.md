# Mode clavier Arrangeur

Si vous avez un clavier Midi connecté via Midi IN, vous pouvez l’utiliser comme un (pseudo) clavier arrangeur: JJazzLab reconnaîtra les symboles d’accords joués et mettra à jour la piste d’accompagnement en conséquence.

{% hint style="danger" %}
**Ce mode est uniquement à des fins éducatives.**&#x20;

Il y aura un délai entre votre changement d’accord et le changement de musique. C’est normal car JJazzLab n’est pas conçu pour fonctionner comme un clavier arrangeur temps réel.
{% endhint %}

![](../.gitbook/assets/Arranger.png)

Connectez d’abord votre clavier Midi à un périphérique Midi IN (voir le panneau **Midi** de **Options/Préférences**).

Créez ou ouvrez un morceau, puis sélectionnez une partie de morceau. La partie morceau sera utilisée par JJazzLab pour savoir quel rythme et quels paramètres rythmiques doivent être utilisés pendant la session en mode arrangeur.

Affichez la fenêtre **Arrangeur** (menu Fenêtre) et appuyez sur son **bouton Play**: la musique devrait maintenant suivre les accords que vous jouez sur votre clavier.

Seules les notes reçues avant la note splittée sont utilisées pour la reconnaissance des symboles d’accords.

{% hint style="info" %}
Pendant que vous jouez, vous pouvez modifier les paramètres rythmiques de la partie active de la chanson (par exemple, changer la variation).
{% endhint %}
