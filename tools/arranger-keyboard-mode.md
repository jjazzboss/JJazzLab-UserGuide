# アレンジャーキーボードモード

MIDI IN経由でMIDIキーボードを接続している場合、MIDIキーボードを（疑似）アレンジャーキーボードとして使用できます：JJazzLabは演奏されたコード記号を認識し、それに応じて伴奏トラックを更新します。

{% hint style="danger" %}
**このモードは教育目的のみに使用されます。**&#x20;

コードチェンジと音楽の変化の間には遅延が生じます。これはJJazzLabがリアルタイムのアレンジャーキーボードとして動作するよう設計されていないため、正常な動作です。
{% endhint %}

![](../.gitbook/assets/Arranger.png)

First connect your Midi keyboard to a Midi IN device (see the **Midi** panel of **Options/Preferences**).

Create or open a song, then select a song part. The song part will be used by JJazzLab to know which rhythm and which rhythm parameters should be used during the arranger mode session.

Display the **Arranger** window (menu Window) and press its **Play** button: music should now follow the chords you play on your keyboard.

Only the notes received below the split note are used for chord symbol recognition.

{% hint style="info" %}
While you play you can change rhythm parameters of the active song part (e.g. change the variation).
{% endhint %}
