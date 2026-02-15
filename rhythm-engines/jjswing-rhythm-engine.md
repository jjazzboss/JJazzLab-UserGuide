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

## リズムパラメータ

jjSwingには2つの特定のリズムパラメータとして、ベーススタイルとドラムスタイルがあります。

### ベーススタイル

可能な値を下の画像で示します。

<figure><img src="../.gitbook/assets/jjSwing-bassStyle.png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="140">ベーススタイル</th><th>説明</th></tr></thead><tbody><tr><td>auto</td><td>実際のベーススタイルはリズムバリエーションによる（例：Main A-1）</td></tr><tr><td>2-feel</td><td>2拍のウォーキングベース</td></tr><tr><td>walking</td><td>ウォーキングベース</td></tr><tr><td>double-note</td><td>多くのダブルノート（繰り返される音）を含むウォーキングベース</td></tr><tr><td>double-time</td><td>ウォーキングベースを2倍速で演奏しつつ、コード進行は元のテンポで維持。ドラムスタイルもダブルタイムに設定されている場合に使用</td></tr><tr><td>intro</td><td>リズムバリエーションIntro Aで使用</td></tr><tr><td>ending</td><td>リズムバリエーションEnding Aで使用</td></tr><tr><td></td><td></td></tr></tbody></table>

### ドラムスタイル

可能な値を下の画像で示します。

<figure><img src="../.gitbook/assets/jjSwing-drumsStyle.png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="140">ドラムスタイル</th><th>説明</th></tr></thead><tbody><tr><td>auto</td><td>実際のドラムスタイルはリズムバリエーションによる（例：Main A-1）</td></tr><tr><td>brushes 1/2</td><td>2種類のブラシベースのドラム</td></tr><tr><td>hi-hat 1/2</td><td>2種類のハイハットベースのドラム</td></tr><tr><td>ride 1/2/3/4</td><td>4種類のライドシンバルベースのドラム</td></tr><tr><td>shuffle 1/2</td><td>2種類の異なる12/8拍子ベースのドラム</td></tr><tr><td>double</td><td>ドラムを倍速で演奏されつつ、コード進行は元のテンポで維持。ベーススタイルもダブルタイムに設定されている場合に使用</td></tr><tr><td>intro</td><td>リズムバリエーションIntro Aで使用</td></tr><tr><td>ending</td><td>リズムバリエーションEnding Aで使用</td></tr></tbody></table>

## 設定

jjSwingの設定は、設定/Rhythms、またはリズム選択ダイアログ(Rhythm selection dialog)で利用可能です。**jjSwing styles**リズムプロバイダーを選択すると、以下のように表示されます。

<figure><img src="../.gitbook/assets/jjSwing-SettingsButton.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/jjSwing-SettingsWindow.png" alt=""><figcaption></figcaption></figure>
