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

The **Interpretation** tab lets you decide how this chord symbol should be played:

* **Normal**
* **Accent**: add a rhythmic accent and randomly a crash cymbal. You can make the accent stronger, or make sure a crash cymbal is played or not played.
* **Hold**: add a rhythmic accent and hold notes until next chord symbol. If extended more instruments are hold.
* **Shot**: add a rhythmic accent with chord notes played briefly. If extended more instruments are shot.
* **Pedal bass**: bass line will only play the bass note \(for ex. F for Fm7 or C for Fm7/C\). This setting is on by default when you enter a slash chord.

{% hint style="info" %}
Each rhythm generation engine may render these Interpretation parameters differently.
{% endhint %}

  
 The shape of the marker below the chord symbol depends on the interpretation mode:

![](../../.gitbook/assets/interpretationmarkers.png)

 For example, in order to render: 

![](../../.gitbook/assets/rhythmicaccents.png)

you could use the following interpretation parameters: 

![](../../.gitbook/assets/examplerhythmicaccents.png)

{% hint style="info" %}
See below the keyboard shortcuts to change the interpretation of selected chords.
{% endhint %}

### Harmony

Select a chord symbol, edit it and select the **Harmony** tab.

![](../../.gitbook/assets/chordsymbolharmonydialog.png)

The **Harmony** tab lets you select the scale to be used when rendering the music for this chord symbol.

**Example** Suppose that the reference bass line for Eb7M contains a Ab \(4th degree of the Eb major scale\). If you select the Lydian mode \(which has a sharp 11th degree\) then the reference bass note Ab will be rendered as A for this chord symbol.

By default no scale is selected: each rhythm generation engine will decide the "best" scale to use.

### Substitute chord symbol

Select a chord symbol, edit it and select the **substitute** chord symbol tab.

![Snapshot to be updated! Alternate &amp;gt; Substitute](../../.gitbook/assets/chordsymbolalternatedialog.png)

This tab lets you define a **substitute** chord symbol which will be used when some conditions are met. 

**Substitute** chord symbols are useful when you need to introduce a slight variation in a part of a song.

The **substitute** chord symbol can be any chord symbol, with any interpretation or harmony, or no chord symbol at all \(void chord\). Chord symbols which have an **substitute** chord symbol defined are displayed with a different color \(see image below\).

_Example:_

In the Carlos Santana's "Europa" song, the 1st ending of the theme is a Cm7, but the 2nd one is a C major. To implement this in JJazzLab, one solution could be to duplicate section A1 to create section A2 with the different ending, then update the song structure accordingly. This is perfectly fine, but when changes are minor the **substitute** chord symbol can provide a simpler solution.

You can see below \(and in the dialog snapshot above\) that a C7M **substitute** chord has been created for Cm7. C7M will be used for all song parts \(see the [song structure editor](song-structure.md)\) where the marker is set to Theme2. On the image below it means the C7M will be used only for the 2nd song part.

![Snapshot to be updated! ALTERNATE &amp;gt; SUBSTITUTE](../../.gitbook/assets/alternatechordleadsheet.png)

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

