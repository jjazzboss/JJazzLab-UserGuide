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

## Default rhythm mix

{% hint style="info" %}
If you often use a certain rhythm, adjust its mix and save it as a **default rhythm mix file**, so that each time you'll use that rhythm in a song, it will sound optimally for your output synth.
{% endhint %}

#### How it works

When you create a song and select a new rhythm (e.g. `MediumJazz.s637.sst`), JJazzLab looks for a **default rhythm mix** file (`MediumJazz.s637.mix`) to initialize the song mix for this rhythm.&#x20;

The default rhythm mix lets you define **an optimized rhythm mix adapted to your output synth** ([FluidSynth ](../sounds/using-fluidsynth.md)or a [custom synth](../sounds/other-synths.md)): for example with`MediumJazz.s637.sst` you can make the electric guitar quieter, replace the default GM bass instrument by a better one available on your synth, and mute that flute you don't like.

{% hint style="warning" %}
**If the default rhythm mix file is not present**, JJazzLab uses the **rhythm's** **builtin mix**. The rhythm's builtin mix is infered from the rhythm data and from your output synth capabilities. With FluidSynth the resulting mix should be OK  with a few manual adjusments. With a custom synth, it might need more fixes.
{% endhint %}

#### Adjusting and saving a default rhythm mix

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
