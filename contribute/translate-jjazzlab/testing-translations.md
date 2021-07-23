---
title: Try JJazzLab with the latest translation files
date: '2018-07-07T09:53:27.000Z'
draft: false
---

# Testing translations

If you can't wait for the next official JJazzLab release, you may want to try JJazzLab with the latest translation files, to see how it looks. 

First you'll need to build JJazzLab-X from the source code, according to [these instructions](https://jjazzlab.gitbook.io/developer-guide/build-from-source-code), but use the **l10n\_master** branch instead of the master branch, as explained below:

### Retrieve the JJazzLab-X code source project from GitHub

1. Menu **Team/Git/Clone**
2. Enter repository address **https://github.com/jjazzboss/JJazzLab-X.git** 
3. Leave user and password blank
4. Press **Next** and select _only_ the branch **l10n\_master** \(l10n means "localization"\)
5. let Netbeans open the **JJazzLab-X** project from the cloned files

{% hint style="info" %}
The **l10n\_master** branch is a localization branch where Crowdin automatically pushes new translation files. Note that this synchronization is done **every hour**, so you may not see the latest changes. Also, if there are several translation candidates for one source phrase, **only the validated one is pushed**. If no translation is validated yet, Crowdin uses the first candidate.
{% endhint %}



