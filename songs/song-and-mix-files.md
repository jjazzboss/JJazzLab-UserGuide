# 楽曲とミックスファイル

**mySong** という名前の曲を保存すると、JJazzLab は実際には２つの異なるファイルを保存します：

* **mySong.sng**: ミックス情報以外のすべてを含みます。具体的には、コードリードシート、ソングストラクチャー、使用したリズムの参照（例: "16beat.s456.sty"）などです。
* **mySong.mix**: ミックス情報のみを含みます。つまり、各トラックがどの楽器を使用しているか、およびどの設定（音量、リバーブ、パンなど）で設定しているかを示します。

なぜ2つの異なるファイルを使うのですか？&#x20;

ミックス情報はシンセ出力固有のものだからです（[FluidSynth](../sounds/using-fluidsynth.md)または[カスタムシンセ](../sounds/other-synths.md)）。ミックスデータを.sngファイルに統合すると、ユーザーごとに異なるシンセ出力を使用しているため、.sngファイルの互換性が失われます。

**mySong.sng**を開くと、JJazzLabは同じディレクトリ内の**mySong.mix**を開こうとします。**mySong.mix**が存在しない場合、JJazzLabは[デフォルトのリズムミックス](song-and-mix-files.md#default-rhythm-mix)ファイルが存在すればそれを使用してミックスを作成します。存在しない場合は、**リズムの組込みミックス**を使用します（詳細は[下記](song-and-mix-files.md#default-rhythm-mix)を参照）。

{% hint style="warning" %}
楽曲ファイル（.sng）を読み込む際、その楽曲で使用されているリズム参照（例：「MediumJazz.s637.sst」）が利用できない場合、JJazzLabはシステム上で利用可能な別のリズムで代用します。JJazzLabは名前に基づいて「類似した」リズム（上記の例では別の「jazz」リズム）を可能な限り探します。適切なリズムが見つからない場合、その拍子記号のデフォルトリズムを使用します。
{% endhint %}

## デフォルトのリズムミックス

{% hint style="info" %}
特定のリズムを頻繁に使用する場合は、そのミックスを調整し、**デフォルトリズムミックスファイル**として保存してください。そうすれば、ソングでそのリズムを使用するたびに、シンセ出力に最適化された音で再生します。
{% endhint %}

#### 仕組み

ソングを作成し新しいリズム（例：`MediumJazz.s637.sst`）を選択すると、JJazzLabはこのリズム用のソングミックスを初期化するために**デフォルトのリズムミックス**ファイル（`MediumJazz.s637.mix`）を検索します。&#x20;

デフォルトのリズムミックスでは、**出力シンセに最適化したリズムミックス**を定義できます（[FluidSynth](../sounds/using-fluidsynth.md)または[カスタムシンセ](../sounds/other-synths.md)を使用する場合）： 例えば`MediumJazz.s637.sst`を使用すると、エレキギターの音量を下げたり、デフォルトのGMベース音源をシンセで利用可能なより良い音源に置き換えたり、好まないフルートの音をミュートしたりできます。

{% hint style="warning" %}
**デフォルトのリズムミックスファイルが存在しない場合**、JJazzLabはリズムの**組込みミックス**を使用します。リズムの組込みミックスは、リズムデータとシンセ出力の能力から推測されます。FluidSynthを使用する場合、結果のミックスは手動調整を数点加えれば問題ないはずです。カスタムシンセを使用する場合は、より多くの修正が必要になる可能性があります。
{% endhint %}

#### デフォルトのリズムミックスの調整と保存

* In the Midi options select your preferred output synth, e.g. [FluidSynth](../sounds/using-fluidsynth.md).&#x20;
* Load a song which uses your favorite rhythm and play it\
  (song mix is initialized with the **rhythm's builtin mix** if no default rhythm mix is defined)
* Adjust the mix until you're satisfied with the song rendering
* Use **Save as default rhythm mix** from the **Mix Console File menu**, as shown below.

<figure><img src="../.gitbook/assets/2024-09-30 22_55_58-JJazzLab  4.1.2-SNAPSHOT.png" alt=""><figcaption></figcaption></figure>

The default rhythm mix file is saved **in the same directory than the rhythm file**.&#x20;

{% hint style="success" %}
JJazzLab will now automatically use this **default rhythm mix** each time you select the corresponding rhythm in a song.
{% endhint %}

If it's defined, you can always reapply a default rhythm mix using **Load default rhythm mix** from the **Mix console menu File**.&#x20;

If you want to reset the song mix to the **rhythm's builtin mix** (see above), use **Reset channels** from the **Mix Console Edit menu**, as shown below.&#x20;

<figure><img src="../.gitbook/assets/2024-09-30 22_26_48-JJazzLab  4.1.2-SNAPSHOT.png" alt=""><figcaption></figcaption></figure>

## Mix file lookup order

Combining the 2 paragraphs above, below is how JJazzLab looks for mix information when you load **myDir/mySong.sng** and this songs uses rhythm **16BeatRock** :

1. use **myDir/mySong.mix** if present<br>
2. use **defaultRhythmMixDir/16BeatRock.mix** if present<br>
3. use **16BeatRock** builtin default mix

Steps 2. and 3. are also used when you add a new rhythm in a song.
