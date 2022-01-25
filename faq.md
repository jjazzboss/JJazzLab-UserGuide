---
description: よく聞かれる質問
---

# FAQ

## JJazzLabが気に入ってて、無料でいてほしいのですが、何かお手伝いできますか？ <a href="#how-to-help" id="how-to-help"></a>

* [寄付 ](https://www.jjazzlab.com/en/donate/)してくださるとJJazzLabがみんなに無料のままでいられます。
* JJazzLab [翻訳 ](contribute/translate-jjazzlab/)を手伝ってください。
* [ご協力 ](contribute/improve-doc.md)は、この文章の改訂でもお願いしています。
* ビデオにいいね！と、 [YouTube チャンネル](https://www.youtube.com/channel/UC0L3SwjY6bhTj6jsbOYzzAw)の登録を！
* あなたがJJazzLabと一緒に演奏しているのを録画して！：そのビデオを、JJazzLabのYouTubeチャンネルに掲載します。
* 口コミ拡散！トークと **www.jjazzlab.com** へのリンクをソーシャルネットワーク、ブログ、ウェブサイトなどで！
* プログラマーなら、 [プログラムコードにご協力を](https://github.com/jjazzboss/JJazzLab-X/blob/master/CONTRIBUTING.md)

## MacOS使いなんですけど、**Tools→Optionsが見当たりませんが?**

MacOSでは、**Options** メインメニューの **JJazzLab→Preferences**からアクセスします。

## 曲の移調はどうするのですか？ <a href="#how-to-transpose-song" id="how-to-transpose-song"></a>

1. コード記号をすべて選択(右クリックメニューの **Select all the chord symbols**)
2. マウスホイールを使うか、右クリックメニューで移調( **Transpose** )

## JJazzLabで伴奏オーディオファイル(.mp3, .wav, etc.)はどうやって作るのですか？ <a href="#generate-mp3" id="generate-mp3"></a>

{% tabs %}
{% tab title="Windows" %}
もし、**VirtualMidiSynth** で[JJazzLabサウンドフォント](configuration/jjazzlab-soundfont/)を鳴らしているなら簡単です：

1. JJazzLabで、伴奏トラックを **File→Export to Midi file**を使って.midファイルで保存します。
2. 次に**VirtualMIDISynth** を起動(Windowsのシステムトレイにあるアイコンを右クリック)し、MIDIファイルを変換( **MIDI converter**)を選択します。.midファイルを選ぶとオーディオファイルが生成されます。

また、スクリーンレコーダーソフトウェアを使用することもできます。コンピュータのサウンドカードの出力を直接キャプチャして、.mp3ファイルに保存するものもあります。
{% endtab %}

{% tab title="Linux" %}
Use the **FluidSynth -F** option to generate a .wav file.
{% endtab %}

{% tab title="VST Instruments" %}
Use the VST host (Cubase, Reaper, etc.) capabilities to record the output of the VST instruments.
{% endtab %}
{% endtabs %}

## 真っ新な再インストールはどうするのですか？

JJazzLabのユーザー設定を全てリセットする必要があります(アンインストール／再インストールでは十分ではありません)。&#x20;

簡単な方法： メニュー **Tools→Options→Advanced** の **Reset all user settings**のボタンです。

難しい方法：メニューの **Help→About→System Information** で **Netbeans user dir** の場所を確認し、 JJazzLabを終了してから **Netbeans user dir**を削除します。

## Windowsの管理者権限がありませんが、JJazzLabをインストールできますか？

はい。JJazzLab インストーラの最初のプロンプトで、「Install only for me」を選択し、書き込み権限のあるインストールディレクトリを選択してください（例：マイドキュメント）。

## サウンドをより良くするにはどうしたらよいでしょうか？

{% hint style="warning" %}
2021年5月更新: スタインバーグ社の新製品「Halion Sonic SE」（無料）をJJazzLabで使うと、とても**良い音**のバッキングトラックができます。詳しくは[JJazzLab フォーラム](https://jjazzlab.freeforums.net/thread/215/new-great-sounds-jjazzlab)で。
{% endhint %}

JJazzLabの出力には、_良いシンセサイザー_が必要です。では、バッキングトラックの生成に必要な良いシンセサイザーとは何か？考慮すべき要素は大きく分けて3つあります：&#x20;

1. **個別の音源品質** (ドラム、ベース、ピアノなどの音源)
2. **サウンド全体のミックス**  (全く違う楽器でも一緒に合わせる)
3. **効果** (全体と楽器ごとの効果)

{% hint style="info" %}
経験上、2.と3.の要素は、1.の要素と同じくらい重要であると考えられます。
{% endhint %}

他にも2つの要素が、バッキングトラックのレンダリングに影響を与えます：

* **Drums XG** **互換性**: ヤマハスタイルでは、ジャズブラシなど、XGのドラム／パーカッションサウンドがたくさん使用されています。
* **JJazzLabでの正しいシンセ出力の設定**: ヤマハスタイルでは、各チャンネルに好ましい楽器（例：シンセベース）を定義します。シンセ出力の設定が間違っていると、JJazzLabは各チャンネルに最適な楽器を選択することができません（例：シンセベースの代わりにピアノの音を使う）。

以下に一般的なコンフィギュレーションをいくつか挙げます。

| シンセ出力                                 | 音質    | コメント                                                                                                                                                                                                                         |
| ------------------------------------- | ----- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Java Internal Synth with default bank | 低     | すぐに使えます。デフォルトのサウンドバンクのサイズが非常に小さいことを考慮すると、全体のサウンドバランスは非常に良いです。                                                                                                                                                                |
| GM サウンドフォント                           | 低～並   | バランスのとれたサウンドフォントを見つけるのが難しい（例：いいピアノが手に入ったが、低音がダメだった、など。楽器ごとのエフェクトがない。XGとの互換性がない。）                                                                                                                                             |
| JJazzLab サウンドフォント                     | 並     | 多くのヤマハスタイルでテスト済み。XGに対応し、さらにいくつかの追加サウンドとドラムキットを搭載しています。Output Synthの設定プリセットがあるので、すぐに設定できます。楽器ごとの個別のエフェクトはありません。                                                                                                               |
| ハードウェアシンセサイザー                         | とても良い | GMモードでは、個々のサウンド間のミックスは、通常、そのままでも非常に良い状態です。個々のサウンドには独自のエフェクト（例：ギターのディストーションなど）をかけることができ、これが全体のレンダリングに大きな影響を与えます。シンセのためのCakewalkインストゥルメント定義ファイル(.ins)がウェブ上にあれば、JJazzLabから直接コントロールすることができます。                                    |
| ソフトウェアシンセサイザー                         | 最高    | 通常、GMとの互換性はありません。バーチャルMIDIデバイス＋VSTホスト、各楽器の音の選択、VSTホストからのミックス調整など、初期設定に手間がかかります...。個々の音にはそれぞれエフェクトがあり（例：ギターのディストーションなど）、これは全体のレンダリングに大きな影響を与えます。Cakewalk のインストゥルメント定義ファイル (.ins) を独自に作成していない限り、リズムを変更する際にはセットアップを調整する必要があります。 |

また、リズムがうまく鳴らないときには、別の楽器を試したり、ミックス（ボリューム、エフェクト、パン、ベロシティシフト）を調整するだけで、驚くほど改善されます。

バッキングトラックを完全にカスタマイズしたい場合は、MIDIファイルにエクスポートし、そのMIDIファイルをお好みのDAWにインポートして高度なカスタマイズを行うことができます。

詳しくは、 [MIDI設定](configuration/midi-configuration.md) のページをご覧ください。

## ヤマハのアレンジャー・キーボード(Tyros, PSR, ...)を持っていますが、どうやればJJazzLabと一緒に使うことができますか？

JJazzLabはあなたのキーボードをドライブして、その最適化されたサウンドを利用することができます。キーボードをMidiで接続し、 [**シンセ出力エディター**](configuration/output-synth.md) で **ヤマハ Tyros** プリセットを適用します。このプリセットはTyros5をベースにしており、以前のTyrosモデルやほとんどのPSRキーボードとの下位互換性があります。

## フォントを大きくするにはどうしたらよいですか？ <a href="#font-bigger" id="font-bigger"></a>

JJazzLab をインストールしたディレクトリで、 **etc/jjazzlab.conf**  ファイルを編集し、**default\_option**変数に**--fontsize 16** (16 またはその他の値、デフォルトは 11)を追加すると、以下のようになるはずです：

`default_options="--branding jjazzlab -J-Djjazzlab.version=2.2.0 -J-Dplugin.manager.check.new.plugins=true -J-Dplugin.manager.check.interval=EVERY_DAY --fontsize 16"`&#x20;

JJazzLab再起動すると、全メニューが大きく見えるはずです。

&#x20;エディターフォントの中には、この設定に依存しないものもあるので、これですべてが解決するわけではありません。しかし、メニューの**Tools/Options/Theme**を使って、そのうちのいくつかを調整することができます。リストの各項目をチェックし、フォントが定義されている場合は、それを変更して大きくします。ユーザー設定は自動的に保存されますので、この作業は一度だけ行う必要があります。

## コマンドライン引数でJJazzLabを起動できますか？

コマンドラインで1つまたは複数の.sngファイル名を渡せば、JJazzLabの起動時にそれらのファイルを開くことができます。

```
# Example on Win10 (x64)
"C:\Program Files\JJazzLab\bin\jjazzlab64.exe" "C:\my dir\MySong.sng" "D:\AnotherSong.sng"
```

## バグの提出方法は？ "log"ファイルはどうやって見つけるの？

バグは[Eメール ](https://www.jjazzlab.com/en/contact/)を送っていただくか、GitHub ユーザーなら [issue](https://github.com/jjazzboss/JJazzLab-X/issues)を作ってください。

サポートするためには、以下の情報が必要です：

* **ログファイル** の内容の提供
* 何が期待通りに動作しないかの記述
* 問題の原因となった一連の動作の記述

{% hint style="info" %}
JJazzLabを起動するたびに、新しい**ログファイル** が作成されます。問題が発生したときに正しいログファイルを取得することが重要です。
{% endhint %}

ログファイルの内容を取得するには：

1. 問題が発生した直後に、メニューの **Tools→Options→Advanced**を開きます。
2. **Show Log Window**をクリック
3. バグリポート内にあるウィンドウの **内容全部** をコピー＆ペースト

何らかの理由で上記が上手くいかない場合は：

1. メニューの **Help→About**に進み、 **Netbeans user dir**を見つけます。\
   Windowsの例 `C:\Users\MyName\AppData\Roaming\jjazzlab\2.2`\
   Linuxの例 `/home/MyName/.jjazzlab/2.2`
2. エクスプローラーを開き、そのディレクトリに進んで、そのサブディレクトリの **var/log** に進みます。
3. 最後のログファイルは、**messages.log**で、１つ前は**messages.log.1**、さらにもう１つ前は、 **messages.log.2**などとなっています。
4. 該当するログファイルを見つけて、バグレポートと一緒に送信してください。

{% hint style="danger" %}
**Netbeans user dir**が見当たらない場合、エクスプローラが隠しファイルを表示するようになっているか確認してください(例. AppData ディレクトリはWindowsでは通常、隠されています)。
{% endhint %}

&#x20;
