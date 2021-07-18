---
title: FAQ
date: '2018-07-07T09:53:27.000Z'
draft: false
weight: 1000
helpTitle: true
toc: true
description: よく聞かれる質問
---

# FAQ

## JJazzLabが気に入ってて、無料でいてほしいのですが、何かお手伝いできますか？ <a id="how-to-help"></a>

* [寄付 ](https://www.jjazzlab.com/en/donate/)してくださるとJJazzLabがみんなに無料のままでいられます。
* JJazzLab [翻訳 ](contribute/translate-jjazzlab/)を手伝ってください。
* [ご協力 ](contribute/improve-doc.md)は、この文章の改訂でもお願いしています。
* ビデオにいいね！と、 [YouTube チャンネル](https://www.youtube.com/channel/UC0L3SwjY6bhTj6jsbOYzzAw)の登録を！
* あなたがJJazzLabと一緒に演奏しているのを録画して！：そのビデオを、JJazzLabのYouTubeチャンネルに掲載します。
* 口コミ拡散！トークと **www.jjazzlab.com** へのリンクをソーシャルネットワーク、ブログ、ウェブサイトなどで！
* プログラマーなら、 [プログラムコードにご協力を](https://github.com/jjazzboss/JJazzLab-X/blob/master/CONTRIBUTING.md)

## MacOS使いなんですけど、**Tools/Optionsが見当たりませんが?**

MacOSでは、**Options** メインメニューの **JJazzLab/Preferences**からアクセスします。

## 曲の移調はどうするのですか？ <a id="how-to-transpose-song"></a>

1. コード記号をすべて選択\(右クリックメニューの **Select all the chord symbols**\)
2. マウスホイールを使うか、右クリックメニューで移調\( **Transpose** \)

## JJazzLabで伴奏オーディオファイル\(.mp3, .wav, etc.\)はどうやって作るのですか？ <a id="generate-mp3"></a>

{% tabs %}
{% tab title="Windows" %}
もし、**VirtualMidiSynth** で[JJazzLab SoundFont](configuration/jjazzlab-soundfont/)を鳴らしているなら簡単です：

1. JJazzLabで、伴奏トラックを **File/Export to Midi file**を使って.midファイルで保存します。
2. 次に**VirtualMIDISynth** を起動\(Windowsのシステムトレイにあるアイコンを右クリック\)し、MIDIファイルを変換\( **MIDI converter**\)を選択します。.midファイルを選ぶとオーディオファイルが生成されます。

また、スクリーンレコーダーソフトウェアを使用することもできます。コンピュータのサウンドカードの出力を直接キャプチャして、.mp3ファイルに保存するものもあります。
{% endtab %}

{% tab title="Linux" %}
Use the **FluidSynth -F** option to generate a .wav file.
{% endtab %}

{% tab title="VST Instruments" %}
Use the VST host \(Cubase, Reaper, etc.\) capabilities to record the output of the VST instruments.
{% endtab %}
{% endtabs %}

## 真っ新な再インストールはどうするのですか？

JJazzLabのユーザー設定を全てリセットする必要があります\(アンインストール／再インストールでは十分ではありません\)。 

簡単な方法： メニュー **Tools/Options/Advanced** の **Reset all user settings**のボタンです。

難しい方法：メニューの **Help/About/System Information** で **Netbeans user dir** の場所を確認し、 JJazzLabを終了してから **Netbeans user dir**を削除します。

## Windowsの管理者権限がありませんが、JJazzLabをインストールできますか？

はい。JJazzLab インストーラの最初のプロンプトで、「Install only for me」を選択し、書き込み権限のあるインストールディレクトリを選択してください（例：マイドキュメント）。

## より良いサウンドはどうしたらよいでしょうか？

{% hint style="warning" %}
2021年5月更新: スタインバーグ社の新製品「Halion Sonic SE」（無料）をJJazzLabで使うと、とても**良い音**のバッキングトラックができます。詳しくは[JJazzLab フォーラム](https://jjazzlab.freeforums.net/thread/215/new-great-sounds-jjazzlab)で。
{% endhint %}

JJazzLabの出力には、_良いシンセサイザー_が必要です。では、バッキングトラックの生成に必要な良いシンセサイザーとは何か？考慮すべき要素は大きく分けて3つあります： 

1. **個別の音源品質** \(ドラム、ベース、ピアノなどの音源\)
2. **サウンド全体のミックス**  \(全く違う楽器でも一緒に合わせる\)
3. **効果** \(全体と楽器ごとの効果\)

{% hint style="info" %}
経験上、2.と3.の要素は、1.の要素と同じくらい重要であると考えられます。
{% endhint %}

他にも2つの要素が、バッキングトラックのレンダリングに影響を与えます：

* **Drums XG** **互換性**: ヤマハスタイルでは、ジャズブラシなど、XGのドラム／パーカッションサウンドがたくさん使用されています。
* **JJazzLabでの正しいシンセ出力の設定**: ヤマハスタイルでは、各チャンネルに好ましい楽器（例：シンセベース）を定義します。シンセ出力の設定が間違っていると、JJazzLabは各チャンネルに最適な楽器を選択することができません（例：シンセベースの代わりにピアノの音を使う）。

以下に一般的なコンフィギュレーションをいくつか挙げます。

| シンセ出力 | 音質 | コメント |
| :--- | :--- | :--- |
| Java Internal Synth with default bank | 低 | すぐに使えます。デフォルトのサウンドバンクのサイズが非常に小さいことを考慮すると、全体のサウンドバランスは非常に良いです。 |
| GM サウンドフォント | 低～並 | バランスのとれたサウンドフォントを見つけるのが難しい（例：いいピアノが手に入ったが、低音がダメだった、など。楽器ごとのエフェクトがない。XGとの互換性がない。）  |
| JJazzLab サウンドフォント | 並 | 多くのヤマハスタイルでテスト済み。XGに対応し、さらにいくつかの追加サウンドとドラムキットを搭載しています。Output Synthの設定プリセットがあるので、すぐに設定できます。楽器ごとの個別のエフェクトはありません。 |
| ハードウェアシンセサイザー | とても良い | GMモードでは、個々のサウンド間のミックスは、通常、そのままでも非常に良い状態です。個々のサウンドには独自のエフェクト（例：ギターのディストーションなど）をかけることができ、これが全体のレンダリングに大きな影響を与えます。シンセのためのCakewalkインストゥルメント定義ファイル\(.ins\)がウェブ上にあれば、JJazzLabから直接コントロールすることができます。 |
| ソフトウェアシンセサイザー | 最高 | 通常、GMとの互換性はありません。バーチャルMIDIデバイス＋VSTホスト、各楽器の音の選択、VSTホストからのミックス調整など、初期設定に手間がかかります...。個々の音にはそれぞれエフェクトがあり（例：ギターのディストーションなど）、これは全体のレンダリングに大きな影響を与えます。Cakewalk のインストゥルメント定義ファイル \(.ins\) を独自に作成していない限り、リズムを変更する際にはセットアップを調整する必要があります。 |

また、リズムがうまく鳴らないときには、別の楽器を試したり、ミックス（ボリューム、エフェクト、パン、ベロシティシフト）を調整するだけで、驚くほど改善されます。

バッキングトラックを完全にカスタマイズしたい場合は、MIDIファイルにエクスポートし、そのMIDIファイルをお好みのDAWにインポートして高度なカスタマイズを行うことができます。

詳しくは、 [Midi configuration](configuration/midi-configuration.md) のページをご覧ください。

## I have a Yamaha arranger keyboard \(Tyros, PSR, ...\), how can I use it with JJazzLab?

JJazzLab can drive your keyboard to benefit from its optimized sounds. Connect your keyboard via Midi and go to the [**Output synth editor**](configuration/output-synth.md) and apply the **Yamaha Tyros** preset. This preset is based on Tyros5 which is backwards compatible with previous Tyros models and most of the PSR keyboards.

## How to make fonts bigger? <a id="font-bigger"></a>

In the JJazzLab installation directory, edit the file **etc/jjazzlab.conf** and add **--fontsize 16** \(16 or any other value, default is 11\) in the **default\_options** variable, you should end up with something like this:

`default_options="--branding jjazzlab -J-Djjazzlab.version=2.2.0 -J-Dplugin.manager.check.new.plugins=true -J-Dplugin.manager.check.interval=EVERY_DAY --fontsize 16"` 

Restart JJazzLab. All menus should look bigger now.

This won't solve everything though, as some editor fonts do not depend on this setting. But you can tweak some of them using menu **Tools/Options/Theme**. Check each item in the list and if there is a font defined, change it to make it bigger. The user settings are automatically saved, so you need to do this only once.

## Can I start JJazzLab with command line arguments?

You can pass one or more .sng file names on the command line, JJazzLab will open them upon start.

```text
# Example on Win10 (x64)
"C:\Program Files\JJazzLab\bin\jjazzlab64.exe" "C:\my dir\MySong.sng" "D:\AnotherSong.sng"
```

## How to submit a bug? How to find the "log" file?

Send an [email ](https://www.jjazzlab.com/en/contact/)or, if you're a GitHub user, create an [issue](https://github.com/jjazzboss/JJazzLab-X/issues).

We need the following information in order to help you:

* Provide the content of the **log file** 
* Describe what does not work as expected
* Describe the sequence of actions that caused the issue

{% hint style="info" %}
A new **log file** is created upon each start of JJazzLab. It's important to get the right log file when the problem occured.
{% endhint %}

To get the log file content:

1. Right after the problem has occured, go to menu **Tools/Options/Advanced**
2. Click on **Show Log Window**
3. Copy & paste **the full content** of this window in your bug report

If for some reason the above does not work:

1. Go to menu **Help/About** and find the location of your **Netbeans user dir**.  For ex. on Windows `C:\Users\MyName\AppData\Roaming\jjazzlab\2.2` For ex. on Linux `/home/MyName/.jjazzlab/2.2`
2. Open an explorer, go to this directory then to the **var/log** subdirectory
3. The last log file is **messages.log**, the previous one is **messages.log.1**, the before previous is **messages.log.2**, etc.
4. Find the relevant log file and send it with your bug report

{% hint style="danger" %}
If you can't find the **Netbeans user dir**., make sure your explorer shows the hidden files \(e.g. the AppData directory is usually hidden on Windows\)
{% endhint %}

 

