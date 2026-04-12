# Rythmes adaptés

Lorsque vous insérez une nouvelle [section](../editeurs/chord-lead-sheet.md#sections) avec une nouvelle signature temporelle, JJazzLab doit sélectionner un rhythm pour la nouvelle [song part](../editeurs/song-structure.md#song-parts).

Si la nouvelle signature temporelle n'a jamais été utilisée auparavant dans le song, JJazzLab essaiera de créer un **rythme adapté** à partir du rhythm actuel (si le rhythm actuel prend en charge cette fonctionnalité). Un **rythme adapté** est simplement le rhythm actuel mais raccourci ou répété pour s'adapter à la nouvelle taille de mesure.

![](../.gitbook/assets/adaptedrhythmexample.png)

Vous remarquerez que le **rythme adapté** n'a pas besoin de canaux supplémentaires dans la mix console : il utilise les canaux Midi de son rhythm source (**fastbossa.s629.prs** dans l'exemple ci-dessus).

Utilisez la [boîte de dialogue de sélection du rhythm](../editeurs/song-structure.md#change-rhythm) pour remplacer un rythme adapté par un rhythm standard (ou vice-versa).

{% hint style="info" %}
Si la signature temporelle a déjà été utilisée dans le song, JJazzLab sélectionnera simplement le dernier rhythm utilisé pour cette signature temporelle.
{% endhint %}
