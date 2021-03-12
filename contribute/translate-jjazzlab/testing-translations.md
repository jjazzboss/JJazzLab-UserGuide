---
title: Try JJazzLab with the latest translation files
date: '2018-07-07T09:53:27.000Z'
draft: false
---

# Testing translations

If you can't wait for the next official JJazzLab release, you may want to try JJazzLab with the latest translation files, to see how it looks.

It's not that simple, but perfectly feasible if you're motivated enough. Below are the steps to follow.

### Make sure you have Java OpenJDK 11 installed

If not, install it from [adoptopenjdk.net](https://adoptopenjdk.net/).

### Download and install Netbeans IDE 12.3 from [Apache Netbeans](https://netbeans.apache.org/) website

This is the development environment and platform on which JJazzLab-X is built.

### Start Netbeans IDE

### Retrieve the JJazzLab-X code source project from GitHub

1. Menu **Team/Git/Clone**
2. Enter repository address **https://github.com/jjazzboss/JJazzLab-X.git** 
3. Leave user and password blank
4. Press **Next** and select _only_ the branch **l10n\_master** \(l10n means "localization"\)
5. let Netbeans open the **JJazzLab-X** project from the cloned files

{% hint style="info" %}
The **l10n\_master** branch is a localization branch where Crowdin automatically pushes new translation files. Note that this synchronization is done **every hour**, so you may not see the latest changes. Also, if there are several translation candidates for one source phrase, **only the validated one is pushed**. If no translation is validated yet, Crowdin uses the first candidate.
{% endhint %}

### Build the JJazzLab-X application

1. Select the **JJazzLab-X** project, right-click **Build**.  When it's done you should see "BUILD SUCCESSFUL" in the **Output** window.

### Run JJazzLab-X

1. Select the **JJazzLab-X** project, right-click **Run**.

JJazzLab-X should start with the default language set up for your computer, e.g. if you use Windows in the German language, you should see JJazzLab in German. If a source phrase is not translated in the target language, the English one is used.

{% hint style="danger" %}
* The application will have no branding and no rhythms, this is normal, those come with the JJazzLab distribution
* The main menu bar \(File, Edit, Tools, Window, Help, Check for updates\) and a few window popup-menus will remain in English, this is also normal
{% endhint %}

### Force JJazzLab-X to run with a different language

You can't switch the language from within the JJazzLab-X application when it is run from Netbeans IDE. But it's still possible to change language for test purposes:

1. In Netbeans, **Projects** tab, open the **JJazzLab-X** project, then the **Important Files** folder
2. Open **Project Properties**
3. Find "**run.args.extra=...**" and insert "**--locale xx:XX** " right after the "=" For example: "**run.args.extra=--locale fr:FR \**"

Use fr:FR for French, de:DE for German, en:US for English, it:IT for Italian, es:ES for Spanish, ja:JP for Japanese, zh:CN for Chinese \(mandarin\).

