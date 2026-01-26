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

以下の通り、**設定/Rhythms**パネルで**Rescan**を強制実行できます。

<figure><img src="../.gitbook/assets/2024-08-22 23_28_07-JJazzLab  4.1.0a.png" alt=""><figcaption><p>設定/RhythmsパネルのRescanボタン</p></figcaption></figure>

{% hint style="info" %}
**ユーザー用リズムファイルディレクトリ**内のリズムを整理するために、最大**2階層のサブディレクトリ**を使用できます。アンダースコア「**\_**」で始まるサブディレクトリはスキャンされません。
{% endhint %}

このキャッシュファイルは、次回の起動時に**リズムリスト**を取得するために使用します。これは最初のスキャンよりもはるかに高速です。特にリズムファイルが多い場合に効果的です。&#x20;

{% hint style="danger" %}
ウェブ上で見つかるヤマハスタイルファイルの品質は大きく異なります。さらに一部のスタイルは

時折「破損」（無効なファイル形式）しており、JJazzLabで読み込めない場合があります。
{% endhint %}

## 新しいリズムファイルの追加 <a href="#adding-new-rhythm-files" id="adding-new-rhythm-files"></a>

**設定/Rhythms**パネル（または[リズム選択ダイアログ](../editors/song-structure.md#change-rhythm-music-style)）から **Add Rhythms...** ボタンを使用します。

<figure><img src="../.gitbook/assets/2024-08-22 22_16_57-JJazzLab  4.1.0a.png" alt=""><figcaption><p>設定/RhythmsパネルのAdd Rhythms...ボタン</p></figcaption></figure>

追加されたリズムファイルは、**リズムファイル用ユーザーディレクトリ**のルートにコピーされて、次回の起動時に**再スキャン**を予定します。

以下の **Add Rhythms...** ダイアログでは、リズムを **現在のセッションのみに追加する** ことを選択できます。つまり、リズムファイルは**リズムファイル用ユーザーディレクトリ**にはコピーされません。

<figure><img src="../.gitbook/assets/2024-08-22 22_19_41-JJazzLab  4.1.0a.png" alt=""><figcaption><p>現在のセッションに対してのみリズムファイルを追加できます</p></figcaption></figure>

{% hint style="danger" %}
**JJazzLab以外** でリズムディレクトリ構造内のリズムファイルを追加または削除した場合、**必ず手動で再スキャンを強制実行してください**。そうしないと、追加/削除されたファイルが反映されません。
{% endhint %}
