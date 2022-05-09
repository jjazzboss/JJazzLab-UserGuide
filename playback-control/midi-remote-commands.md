# MIDIリモートコマンド

コンピューターにMIDIコントローラーを接続すれば、それを使ってJJazzLabの再生をコントロールすることができます。

例えば、ピアノの鍵盤を押すだけで、再生を開始／一時停止したり、次のソングパートにスキップしたりすることができます。

![](https://4052793571-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MQE7B7yjVY3xzlsorS4-887967055%2Fuploads%2FvA8km4zLrfwqjLo3oTg8%2FOptionsMidiIn.png?alt=media\&token=685fc8bb-fa73-4aaf-9633-26cdafec6712)

MIDI INによるリモートコントロールは、上記のように**Options/Preferences**の**MIDI**パネルで設定します。

デフォルトでは、各コマンドは特定の入力音がきっかけになるように設定されています。例えば、C1ノート（MIDIピッチ=24）を受信すると、play/pauseコマンドがきっかけとなります。

コマンドを別の音にしたり、または別のMIDIメッセージに設定するには、コマンドを選択し、**MIDI Learn**を使用します。

**MIDI learn**ボタンを押すと、JJazzLabは数秒間リスニングモードになります。この時間を利用して、コマンドのきっかけとするMIDIメッセージを送信してください。例えば、MIDIキーボードがあって、ノートを変更したい場合は、ノートを押すだけでよいでしょう。パッド付きのMIDIコントローラーがある場合は、使いたいパッドをアクティベートするだけです。

JJazzLabは、選択したコマンドに関連する、受信したMIDIメッセージを表示します。MIDIメッセージが1つのノートに対応している場合、そのノートが表示されます。
