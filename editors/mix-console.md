# ミックスコンソール

**ミックスコンソール** の使い方

* 楽器の変更
* チャンネル設定の調整：音量、リバーブ、コーラス、パン、移調、ベロシティオフセット
* チャンネルをミュートまたはソロにする
* ユーザートラックを追加する
* .mixファイルの読み込み/保存
* さらに：MIDIチャンネルの変更、特殊なMIDIコマンドの使用、MIDIファイルへのエクスポートなど。

JJazzLabは、**ミックスコンソール**の情報を使用して、関連するMIDIメッセージをシンセ出力に送信します。これは、ミックスコンソールで変更を加えるたびに、または再生を開始するたびに実行されます。

{% hint style="danger" %}
MIDIには16のMIDIチャンネルしかありません。そのため、通常1曲に2つ以上のリズムトラックを配置することはできません。
{% endhint %}

![](<../.gitbook/assets/2023-12-31 21_37_13-JJazzLab  4.0.2.png>)

各ミックスコンソールのトラックには、トラックの音を表す下部の **overview component**があります。

## ミックスコンソールツールバー

![](../.gitbook/assets/MixConsoleToolbar.png)

* **Master volume**: MIDI音量を増減します。
* **M**: すべてのトラックでミュートまたはミュート解除します。
* **S**: ソロトラック以外すべてをオフにします。
* **Panic**: MIDIパニックメッセージを送信し、すべてのノートをOFFに切り替えます。
* **Add a User track**: 下の[ユーザートラック](mix-console.md#user-tracks)を参照してください。

## ミックスコンソールメニューバー

### File

*   **Load/Save Default Rhythm Mix** &#x20;

    現在のソングミックスを、デフォルトのリズムミックスファイルを読み込むことで更新します。
    現在のソングミックスをデフォルトのリズムミックスファイルとして保存することもできます。これにより、同じリズムを使用する曲を作成するたびに、デフォルトでこのファイルが再利用されます。 詳しいことはこちら[default rhythm mix files](../songs/song-and-mix-files.md#default-rhythm-mix)で。
*   **Import Mix...** &#x20;

    現在のミックスとインポートされたミックスで共通する楽器の設定のみがインポートされることに注意してください。

### 編集

*   **Reset channels** &#x20;

    各ミックスコンソールのチャンネル（楽器、音量、パン、エフェクト）をデフォルトのリズム設定に復元します。

### Midi

*   **すべてのMIDIパラメーターを有効化** &#x20;

    デフォルトでは、すべてのMIDIパラメータが有効になっています。
    シンセ出力上で直接ミックスを制御したい場合は「すべてのMIDIパラメーターを無効にする」を使用してください：このモードではJJazzLabは_MIDIノートメッセージ_のみを送信し、バンク/プログラムチェンジ、音量、パン、エフェクト関連のMIDIメッセージは送信しません.
*   **Send GM/GM2/XG/GM mode ON message** &#x20;

    これにより、シンセ出力を目的のモードに切り替える特別なMIDI初期化メッセージを送信できます。

## Change instrument

Click on the instrument name in the channel. Note that this is also where instrument transposition can be adjusted.

![](../.gitbook/assets/mixconsole-instrumentselection.png)

## Channel settings

Use the channel settings to:

*   **Add a Midi velocity offset to all notes played on this channel** &#x20;

    Note that this is slightly different from adjusting the volume.<br>
*   **Disable sending specific Midi messages** &#x20;

    Probably because you control the parameter yourself directly on the [output synth](/broken/pages/-MQNBJUwiJ9pkXF9j5Ey).<br>
*   **Enable a drums channel with a Midi channel different than 10**

    If you use a basic GM output synth, it can play drums **only on channel 10**. If drums/percussion are used on other channels in your mix,  you need to activate drums rerouting on these channels. Note that JJazzLab may activate this option for you if it detects, based on the current [output synth](/broken/pages/-MQNBJUwiJ9pkXF9j5Ey) information, potential issues. \
    <br>

![](../.gitbook/assets/mixconsole-channelsettings.png)

## Midi channel

Each Midi channel can be changed manually, just click on the channel number.

![](../.gitbook/assets/MixConsole-ChangeChannel.png)

## User tracks

A user track lets you add your own Midi content to your song: a melody, horn riffs, percussion, etc.

{% hint style="info" %}
If you want to customize a rhythm track only for a song part (e.g. simplify the style's bass phrase for the 2nd verse of your song), you need to use the [Custom phrase rhythm parameter](song-structure.md#rhythm-parameters).
{% endhint %}

#### Adding user tracks

Click the + button in the mix console toolbar to add a new user track. This will also open the [notes editor](notes-editor.md) to edit this user track.

<figure><img src="../.gitbook/assets/2023-12-31 22_01_24-JJazzLab  4.0.2.png" alt=""><figcaption><p>Add user track button</p></figcaption></figure>

You can also clone a rhythm track as a new user track using the + sign in upper right corner of a track overview, as shown below. The original rhythm track will be automatically muted.

<figure><img src="../.gitbook/assets/2023-12-31 21_58_28-JJazzLab  4.0.2.png" alt=""><figcaption><p>Clone a rhythm track as a new user track</p></figcaption></figure>

{% hint style="warning" %}
If you select a drums or percussion instrument for the user track, _and_ your output synth is a basic GM-compatible synth: [set the user track channel](mix-console.md#midi-channel) to 10, and if channel 10 is already used by another track, activate the _Drums rerouting to channel 10_ (see [Channel settings](mix-console.md#channel-settings)) in your User track.
{% endhint %}

#### Edit a user track

Edit the user track by clicking on the upper left icon in the user track overview component, as shown below.&#x20;

This will open the [notes editor](notes-editor.md).

<figure><img src="../.gitbook/assets/2023-12-31 22_02_16-JJazzLab  4.0.2.png" alt=""><figcaption></figcaption></figure>

A user track has always the same length than your song.

{% hint style="danger" %}
If you edit a user track, then make the song shorter (e.g. by removing a song part), the user track will be trimmed to the new song size.
{% endhint %}

## Export to Midi file with mouse drag & drop

You can export the **full backing track** to a Midi file by mouse-dragging from the empty area of the mix console. Note that this is the same as the menu File/Export to Midi file, except it's more convenient when you work with another software such as a DAW.

To export a **single track**, start the mouse-drag from the track icon or track overview component.

![Export a single track with mouse drag & drop](../.gitbook/assets/MixConsoleDragTrack.png)

## Multi-rhythm songs

When a song uses 2 or more rhythms, a popup is displayed in the upper left corner of the mix console to select the rhythm you want to display.

![](../.gitbook/assets/mixconsole-rhythmselectionpopup.png)

Note that some commands such as menu **Edit/Reset channels** will not be applied to the hidden rhythm(s).

## Mouse shortcuts

| Selection                    | Mouse              | Action                        |
| ---------------------------- | ------------------ | ----------------------------- |
| channel volume slider, knobs | double-click       | Input value with keyboard     |
| channel volume slider        | shift + mouse-drag | change volume of all channels |
