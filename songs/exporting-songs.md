# ソングのエクスポート

エクスポートするファイルは、現在の再生設定に対応しています：

* [シンセ出力](../sounds/other-synths.md) 設定
* [ミックスコンソール](../editors/mix-console.md) の設定（トラックの楽器、音量、ミュート状態など）
* [プレカウント、クリック、テンポ](../playback-control/commands.md)設定
* [再生キー移調](../tools/chord-symbols-transposition.md)の設定

## MIDIへのエクスポート

メニューの **ファイル/MIDIファイルにエクスポート...** から、曲全体をMIDI形式で書き出すことができます。**&#x20;

また、[ミックスコンソールからマウスドラッグ](../editors/mix-console.md#export-to-midi-file-with-mouse-drag-and-drop) によって個々のトラックをエクスポートすることもできます。

#### MIDIファイル形式

エクスポートするファイルはマルチトラックのタイプ1 MIDIファイルです。&#x20;

各楽器トラック（トラック1から）は、対応するミックスコンソールトラック設定を使用して初期化します。トラック0には以下が含まれます：

* 必要に応じて、GM/GM2/GS/XG MIDI初期化メッセージ（シンセ出力の設定に依存）
* テンポと拍子のイベント
* コード記号のマーカー

## オーディオへのエクスポート

メニューの **ファイル/Export to Audio file......** から、曲全体を **.wav** または **.mp3** ファイルとしてエクスポートできます。

{% hint style="danger" %}
オーディオエクスポートは、内部の[Fluidsynthシンセ出力](../sounds/using-fluidsynth.md)を使用する場合にのみ利用可能です。
{% endhint %}

**Separate tracks**オプションをチェックすると、各トラックごとに1つのオーディオファイルとしてエクスポートします。下図のように設定してください。

<figure><img src="../.gitbook/assets/2024-12-06 18_39_56-Export to audio file.png" alt=""><figcaption></figcaption></figure>





