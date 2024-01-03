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

## JJazzLabでVST/AUプラグインは使えますか？？

ただし、JJazzLabはVSTプラグインをホストできないため、直接は使用できません。

1. バーチャルMIDIデバイスとVSTホストソフトウェアをコンピュータにインストールしてください。Windows、Linux、Mac用の無料のアプリケーションがウェブ上にあります。例えば、Windowsでは**loopMID**I（高度な設定でフィードバック検出無効にすることをお勧めします）、**SoundBridge**を使用します。
2. JJazzLabの**MIDIオプション**で、**MIDI出力デバイス**を**loopMIDI**に設定します。
3. VSTホストソフトウェアで、**MIDIインデバイス**を**loopMIDI**に設定し、VSTホストとVSTプラグインがすべてのMIDIチャンネル（1〜16）を受信するように設定されていることを確認します。
4. JJazzLabで曲を再生すると、VSTインストゥルメントが聞こえるはずです。

## 真っ新な再インストールはどうするのですか？

JJazzLabのユーザー設定を全てリセットする必要があります(アンインストール／再インストールでは十分ではありません)。&#x20;

簡単な方法： メニュー **Tools→Options→Advanced** の **Reset all user settings**のボタンです。

難しい方法：メニューの **Help→About→System Information** で **Netbeans user dir** の場所を確認し、 JJazzLabを終了してから **Netbeans user dir**を削除します。

## Windowsの管理者権限がありませんが、JJazzLabをインストールできますか？

はい。JJazzLab インストーラの最初のプロンプトで、「Install only for me」を選択し、書き込み権限のあるインストールディレクトリを選択してください（例：マイドキュメント）。

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
