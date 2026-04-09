# Tester des traductions

ISi vous ne pouvez pas attendre la prochaine version officielle de JJazzLab, vous pouvez essayer JJazzLab avec les derniers fichiers de traduction, pour voir à quoi cela ressemble.&#x20;

Vous devrez d’abord construire JJazzLab-X à partir du code source, selon [ces instructions](https://jjazzlab.gitbook.io/developer-guide/build-from-source-code) mais utilisez le l10n\_master branch au lieu de la branche principale, comme expliqué ci-dessous:

### R**écupérer le projet source de code JJazzLab-X à partir de GitHub**

1. Menu **Team/Git/Clone**
2. Entrez l’adresse du référentiel: **https://github.com/jjazzboss/JJazzLab-X.git**&#x20;
3. Laissez l’utilisateur et le mot de passe vides
4. **Appuyez sur Suivant** et sélectionnez _uniquement_ la branche l10n\_master (l10n signifie "localisation")
5. laissez Netbeans ouvrir le projet **JJazzLab-X** à partir des fichiers clonés

{% hint style="info" %}
La branche **l10n\_master** est une branche de localisation où Crowdin pousse automatiquement les nouveaux fichiers de traduction. Notez que cette synchronisation est effectuée **toutes les heures**, de sorte que vous ne pouvez pas voir les dernières modifications. De plus, s’il y a plusieurs candidats à la traduction pour une phrase source, **seule la phrase validée est permise**. Si aucune traduction n’est encore validée, Crowdin utilise le premier candidat.
{% endhint %}

