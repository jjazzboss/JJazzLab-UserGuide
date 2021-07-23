---
title: Chord Leadsheet Editor
date: '2017-10-17T15:26:15.000Z'
draft: false
weight: 310
helpTitle: false
---

# コードリードシート

**コードリードシートエディター** \(Chord lead sheet editor\)を使用する場面は、：

* コード記号の追加: 例 **Cm6, Ab7**
* セクションの追加: 例 **"A"、"B"、"ヴァース"、"コーラス**"...など
* コードの移動や編集による、リズムのアクセント、解釈、ハーモニーの調整

![](../../.gitbook/assets/chordleadsheeteditor.png)

## コード記号

### 入力

小節またはコード記号を選択します。：

* コード記号の最初の文字（A～G）を入力する、または
* ENTERキーを押す、または
* ダブルクリック、または
* 右クリックメニューで「編集」

また、既存のコード記号を選択してコントロールボタンを押しながら移動すると、編集可能な新しいコピーが作成されます。

コード記号の移動は、コード記号を選択してマウスで移動させます。

リードシートのサイズを変更するには、小節を選択して右クリックメニューから**Set end bar**を選択します。

複数選択する場合はctrl+clickまたはshift+clickを使用してください。

{% hint style="info" %}
最初からリードシートを入力するには、最初の小節を選択し、コード記号を直接入力してENTERを押し（自動的に次の小節が選択されます）、2番目の小節のコード記号を入力する、などの方法が簡単です。
{% endhint %}

### 様々なコード表記

JJazzLabでは、各コード記号に対して多くの別名を認識しています。例えば、C7MはCmaj7、Cma7、CM7、CMAJ7などと書くことができます。

別名を追加するには、メニューから **Options→Chord Symbols**を選択します。

### 解釈\(Interpretation\)

コード記号を選択して、編集（ダブルクリック、エンターキー、または右クリックメニュー）にある、**Interpretation**タブを選択します。

![](../../.gitbook/assets/chordsymbolinterpretationdialog.png)

**解釈\(Interpretation\)**タブでは、このコード・シンボルをどのように演奏するかを決定します:

* **Normal**\(通常\)
* **Accent**\(アクセント\): リズミカルなアクセントを加え、クラッシュシンバルをランダムに演奏します。アクセントを強くしたり、クラッシュシンバルを鳴らしたり鳴らさなかったりすることができます。
* **Hold**\(持続\): リズミカルなアクセントを加え、次のコード記号まで音を持続します。拡張\(Extended\)した場合、より多くの楽器を持続します。
* **Shot**\(ショット\): リズミカルなアクセントを加え、コード音を短く演奏します。拡張\(Extended\)した場合、より多くの楽器のショットになります。
* **Pedal bass**\(ペダルベース\): ベースラインでベース音のみを演奏します（例：Fm7ならF、Fm7/CならC）。この設定は、スラッシュコードを入力したときにデフォルトでオンになります。

{% hint style="info" %}
リズム生成エンジンによって、これらの解釈パラメーターの表示が異なる場合があります。
{% endhint %}

  
 コード記号の下に表示されるマーカーの形状は、解釈モードによって異なってきます:

![](../../.gitbook/assets/interpretationmarkers.png)

例えば、このように表現するためには : 

![](../../.gitbook/assets/rhythmicaccents.png)

次のような解釈パラメーターが使用できるでしょう。: 

![](../../.gitbook/assets/examplerhythmicaccents.png)

{% hint style="info" %}
選択したコードの解釈を変更するキーボードショートカットは下の方を参照してください。
{% endhint %}

### モードスケール\(Harmony\)

モードスケールを設定するには、コード記号を選択して編集にある**Harmony**タブを選びます。

![](../../.gitbook/assets/chordsymbolharmonydialog.png)

この**Harmony**タブでは、選んだコード記号を表現する際に使用するスケールを選択できます。

**例** Eb△7のときに、基準のベースラインに、Ab（Ebメジャースケールの4度）が含まれているとします。リディアンモード（\#11度がある）を選択した場合、このコード記号の基準のベース音AbはAとして演奏されます。

初期設定では音階は選択されていません。各リズム生成エンジンが「最適な」音階を決定します。

### コードの代替

代替のコードを設定するには、コード記号を選択して編集にある**substitute** タブを選びます。

![&#x3053;&#x308C;&#x306F;&#x53E4;&#x3044;&#x753B;&#x50CF;&#x3067;&#x3059;&#x3002;Substitute&#x3068;&#x306A;&#x308B;&#x3079;&#x304D;&#x3068;&#x3053;&#x308D;&#x304C;Alternate&#x306B;&#x306A;&#x3063;&#x3066;&#x3044;&#x307E;&#x3059;&#x3002;](../../.gitbook/assets/chordsymbolalternatedialog.png)

このタブでは、いくつかの条件が満たされたときに使用される**代替\(Substitute\)**可能なコード記号を定義できます。 

**代替**コード記号は、曲の一部にちょっとした変化をつけたいときに便利です。

**代替**コード記号は、どんなコード記号でも、どんな解釈でも、どんなハーモニーでも構いません。また、コード記号が全くない状態（voidコード）も可能です。**代替**コード記号が定義されているコード記号は、別の色で表示されます。（下の画像参照）。

_例：_

カルロス・サンタナの「哀愁のヨーロッパ」では、テーマの1回目のエンディングはCm7ですが、2回目のエンディングはCM7です。これをJJazzLabで実現するには、セクションA1を複製して、異なるエンディングを持つセクションA2を作り、それに合わせて曲の構成を変更するという方法があります。この方法でも問題はありませんが、変更がわずかな場合には、**代替**コード記号を使う方がより簡単でしょう。

下の図（および上のダイアログのスナップショット）では、CM7の**代替**コードが作成されています。CM7は、曲のすべてのパートで使用されます（[ソング構成エディター](song-structure.md)\) 。 マーカーがテーマ\(Theme\)2に設定されている部分です。下の画像では、CM7は2つ目のソングパートでのみ使用されることを意味します。

![&#x3053;&#x308C;&#x306F;&#x53E4;&#x3044;&#x753B;&#x50CF;&#x3067;&#x3059;&#x3002;Substitute&#x3068;&#x306A;&#x308B;&#x3079;&#x304D;&#x3068;&#x3053;&#x308D;&#x304C;Alternate&#x306B;&#x306A;&#x3063;&#x3066;&#x3044;&#x307E;&#x3059;&#x3002;](../../.gitbook/assets/alternatechordleadsheet.png)

There is another **substitute** chord symbol example in the 3rd bar: A7. If you listen to the original song you'll notice that they play a A7 on the last beat of the 3rd bar only during solos. So the A7 chord symbol defines its **substitute** chord symbol as the "void chord symbol" \(same as no chord symbol\) when marker is _not_ "Solo".

## Sections input

Typical sections are 'intro', 'verse', 'chorus', etc.

A Song section is the basic unit used by JJazzLab to define the song structure. There is always a section defined on the first bar.

To add a section select a bar which is not after the end then:

* press ENTER, or
* double-click, or
* right-click menu, Edit

The new section name must be different than the existing one.

### Force a section at new line

You can force a section which is not on the first bar of a row to start on the next line. This can be useful when some sections have an odd number of bars.

Select a bar with a section defined or select the section itself, right-click menu "Force Section at New Line".

![](../../.gitbook/assets/forcesectionnewline1.png)

  This will result in the display below. 

![](../../.gitbook/assets/forcesectionnewline2.png)

## Mouse shortcuts

| Selection | Mouse | Action |
| :--- | :--- | :--- |
| bar, chord symbol, section | click | select |
| chord symbol | double click | edit using chord symbol editor |
| bar, section | double click | edit using bar editor |
| bar, chord symbol, section | right-click | popup menu |
| chord symbol | mouse-wheel | transpose |
| editor | ctrl mouse-wheel | change X zoom factor |

## Keyboard shortcuts

{% hint style="info" %}
Many actions are also available via the context menu \(right-click on Windows/Linux, ctrl-click on Mac\), and when available the associated keyboard is displayed.
{% endhint %}

| Selection | Key | Action |
| :--- | :--- | :--- |
| chord Symbol | enter | edit with chord symbol editor |
| bar, section | enter        | edit with bar editor dialog |
| bar  | ctrl-E | set end bar |
| bar | I | insert bars |
| bar | delete | clear bar contents |
| chord symbol, section | delete | remove |
| chord symbol, section | ctrl-left/right | move item one bar left/right |
| bar | shift-delete | remove |
| chord symbol | ctrl-up/down | transpose |
| chord symbol | P | change interpretation |
| chord symbol | S | stronger accent |
| chord symbol | H | crash cymbal/no crash |
| chord symbol | X | hold/shot more instruments |
| chord symbol, section | ctrl-A | select all in section, then in lead sheet |
| bar, chord symbol, section | ctrl-C/X/V | copy/cut/paste items |
| editor | ctrl-Z/Y | undo/redo |
| editor | ctrl-O | set song active \(On/Off\) |
| editor | ctrl-W | close song |

