# Rhythm files

{% hint style="info" %}
In JJazzLab "**rhythm**" usually means a **music style**, like pop or bossa-nova.
{% endhint %}

Rhythms are used by [songs](/broken/pages/-MQSAgDkeWdxuJiOjnJj). Many songs use only one rhythm (e.g. rock), but some may use 2 or more. A song file (.sng) does not contain all the rhythm data, it just keeps a reference to the rhythm's name.&#x20;

Upon first start, JJazzLab [scans ](rhythm-files.md#rhythm-files-scanning)the computer to get a list of the available rhythms.&#x20;

In JJazzLab core, rhythms are made available by [rhythm engines](../rhythm-engines/overview.md). Some rhythms can be based on **rhythm files**. For example the [YamJJazz rhythm engine](../rhythm-engines/yamjjazz-rhythm-engine/) provides rhythms built from Yamaha style files such as **poprock.sty** or **TripHop.S510.prs**.

## Rhythm files location <a href="#rhythm-files-location" id="rhythm-files-location"></a>

JJazzLab expects rhythm files to be in the **User directory for rhythm files**. The location of this directory can be changed in the **Options/Rhythms**, as shown below.&#x20;

![](../.gitbook/assets/userdirforrhythmfiles.png)

## Rhythm files scanning <a href="#rhythm-files-scanning" id="rhythm-files-scanning"></a>

Your **rhythm files** are scanned at startup only upon a fresh install or an upgrade, and the rhythm list is saved into a **cache file**.

You can force a **rescan** in the **Options/Rhythms** panel as shown below.

<figure><img src="../.gitbook/assets/2024-08-22 23_28_07-JJazzLab  4.1.0a.png" alt=""><figcaption><p>Rescan button in the Options/Rhythms panel</p></figcaption></figure>

{% hint style="info" %}
You can use up to **2 levels of sub-directorie**s to organize the rhythms in the **User directory for rhythm files**. Sub-directories whose name starts with an underscore '**\_**' are **not** scanned.
{% endhint %}

This cache file is then used to get the **rhythm list** upon next startups, which is much faster than the initial scanning -especially if you have many rhythm files.&#x20;

{% hint style="danger" %}
Quality of Yamaha style files found on the web vary a lot. Furthermore some styles are&#x20;

sometimes “broken” (invalid file format), i.e. can't be loaded by JJazzLab.
{% endhint %}

## Adding new rhythm files <a href="#adding-new-rhythm-files" id="adding-new-rhythm-files"></a>

Use the **Add Rhythms...** button from the **Options/Rhythms** panel (or from the [Rhythm selection dialog](../editors/song-structure.md#change-rhythm-music-style)).

<figure><img src="../.gitbook/assets/2024-08-22 22_16_57-JJazzLab  4.1.0a.png" alt=""><figcaption><p>Add Rhythms... button in the Options/Rhythms panel</p></figcaption></figure>

Added rhythm files will be copied to the root of the **User directory for rhythm files**, and a **rescan** will be planned on next start.

In the **Add Rhythms...** dialog shown below, you can choose to add the rhythms **for the current session only**, i.e. rhythm files will NOT be copied in the **User directory for rhythm files**.

<figure><img src="../.gitbook/assets/2024-08-22 22_19_41-JJazzLab  4.1.0a.png" alt=""><figcaption><p>You may add rhythm files only for the current session</p></figcaption></figure>

{% hint style="danger" %}
If, **outside of JJazzLab**, you add or remove rhythm files in the rhythm directory structure, **you MUST manually force a rescan**, otherwise the added/removed files will not be taken into account.
{% endhint %}
