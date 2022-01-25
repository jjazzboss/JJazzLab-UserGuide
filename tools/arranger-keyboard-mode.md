# アレンジャーキーボードモード

If you have a Midi keyboard connected via Midi IN, you can use it as a (pseudo) arranger keyboard: JJazzLab will recognize the chord symbols played and update the backing track accordingly.

{% hint style="danger" %}
**This mode if for educational purpose only.**

There will be a delay between your chord change and the music change. This is normal because JJazzLab is not designed to work as a realtime arranger keyboard.
{% endhint %}

![](https://4052793571-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MQE7B7yjVY3xzlsorS4-887967055%2Fuploads%2FT07PJojzjBeanQroiCz1%2FArranger.png?alt=media\&token=678b3c45-dbed-4ad8-b7fd-0f77d61d5fbf)

First connect your Midi keyboard to a Midi IN device (see the **Midi** panel of **Options/Preferences**).

Create or open a song, then select a song part. The song part will be used by JJazzLab to know which rhythm and which rhythm parameters should be used during the arranger mode session.

Display the **Arranger** window (menu Window) and press its **Play** button: music should now follow the chords you play on your keyboard.

Only the notes received below the split note are used for chord symbol recognition.

{% hint style="info" %}
While you play you can change rhythm parameters of the active song part (e.g. change the variation).
{% endhint %}
