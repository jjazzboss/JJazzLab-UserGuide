# リズムファイル

{% hint style="info" %}
JJazzLabでは「**リズム**」は通常、ポップやボサノバのような**音楽スタイル**を指します。
{% endhint %}

リズムは[ソング](/broken/pages/-MQSAgDkeWdxuJiOjnJj)で使用します。多くの楽曲は1つのリズムのみを使用しますが（例：ロック）、2つ以上を使用する場合もあります。楽曲ファイル（.sng）にはリズムデータ全体は含まれず、リズム名への参照のみを保持します。&#x20;

初回起動時、JJazzLabはコンピュータをスキャンし、利用可能なリズムの一覧を取得します。&#x20;

JJazzLabコアでは、リズムは[リズムエンジン](../rhythm-engines/overview.md)が提供します。一部のリズムは**リズムファイル**に基づいています。例えば、[YamJJazzリズムエンジン](../rhythm-engines/yamjjazz-rhythm-engine/)は、**poprock.sty**や**TripHop.S510.prs**といったヤマハスタイルファイルから構築されたリズムを提供します。

## リズムファイルの場所 <a href="#rhythm-files-location" id="rhythm-files-location"></a>

JJazzLabはリズムファイルを**User directory for rhythm files**に配置することを想定しています。このディレクトリの場所は、以下に示すように**設定/Rhythms**で変更できます。&#x20;

![](../.gitbook/assets/userdirforrhythmfiles.png)

## リズムファイルのスキャン <a href="#rhythm-files-scanning" id="rhythm-files-scanning"></a>

**リズムファイル**は、新規インストール時またはアップグレード時のみ起動時にスキャンを行い、リズムリストは**キャッシュファイル**に保存します。

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
