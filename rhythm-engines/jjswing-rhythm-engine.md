---
内容：ジャズスタンダードを練習するための究極のスタイル
---

# jjSwingリズムエンジン

**jjSwing**の特徴は以下の通りです：

* テンポにより自動調整する**リアルなウォーキングベースとメロディックライン**
* 11種類のドラムバリエーション（ブラシ、ハイハット、ライド、シャッフル）
* ダブルタイム機能（元のテンポでコード進行を維持しながら2倍速で演奏）
* ベースとドラムを個別に調整する機能

{% hint style="danger" %}
jjSwingは内部の[FluidSynth](../sounds/using-fluidsynth.md)をシンセ出力として動作するよう最適化しています。別のシンセ出力を使用すると、奇妙な音が聞こえる可能性があります。
{% endhint %}

現在のjjSwingバージョンは4/4拍子のみをサポートしていることに注意してください。ジャズワルツのサポートは後日追加されます。

{% embed url="https://www.youtube.com/watch?v=NZ3VC5GcdiA" %}

## Rhythm parameters

jjSwing has 2 specific rhythm parameters, bass style and drums style.

### Bass style

Possible values are shown in the image below.

<figure><img src="../.gitbook/assets/jjSwing-bassStyle.png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="135">Bass style</th><th>Description</th></tr></thead><tbody><tr><td>auto</td><td>Actual bass style depends on the rhythm variation (e.g. Main A-1)</td></tr><tr><td>2-feel</td><td>Walking in two</td></tr><tr><td>walking</td><td>Walking bass</td></tr><tr><td>double-note</td><td>Walking bass with many double notes (repeated notes)</td></tr><tr><td>double-time</td><td>Walking bass played twice as fast while preserving chord changes at original tempo. This should be used when Drums style is also set to double-time.</td></tr><tr><td>intro</td><td>To be used with rhythm variation Intro A</td></tr><tr><td>ending</td><td>To be used with rhythm variation Ending A</td></tr><tr><td></td><td></td></tr></tbody></table>

### Drums style

Possible values are shown in the image below.

<figure><img src="../.gitbook/assets/jjSwing-drumsStyle.png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="135">Drums style</th><th>Description</th></tr></thead><tbody><tr><td>auto</td><td>Actual drums style will depend on the rhythm variation (e.g. Main A-1)</td></tr><tr><td>brushes 1/2</td><td>2 different brushes-based drums</td></tr><tr><td>hi-hat 1/2</td><td>2 different hi hat-based drums</td></tr><tr><td>ride 1/2/3/4</td><td>4 different ride cymbal-based drums</td></tr><tr><td>shuffle 1/2</td><td>2 different 12/8-based drums</td></tr><tr><td>double</td><td>Drums played twice as fast while preserving chord changes at original tempo. This should be used when Bass style is also set to double-time.</td></tr><tr><td>intro</td><td>To be used with rhythm variation Intro A</td></tr><tr><td>ending</td><td>To be used with rhythm variation Ending A</td></tr></tbody></table>

## Settings

jjSwing settings are available in the Options/Rhythms tab or in the Rhythm selection dialog, when you select the **jjSwing styles** rhythm provider, as shown below.

<figure><img src="../.gitbook/assets/jjSwing-SettingsButton.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/jjSwing-SettingsWindow.png" alt=""><figcaption></figcaption></figure>
