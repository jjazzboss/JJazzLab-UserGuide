---
description: / JJazzLab-X
---

# JJazzLab

{% hint style="info" %}
Want to add or fix documentation? Yes you can!😀 Visit the [Improve documentation](contribute/improve-doc.md) page.
{% endhint %}

![JJazzlab 3](<.gitbook/assets/JJazzLab3.0Full (1).png>)

## Where to start?

Try this very short [video tutorial](video-tutorials.md#for-starters).

## What is JJazzLab?

🎵 JJazzLab is a desktop application which automatically generates backing tracks for any song, even complex ones. It’s a jam buddy to have fun improvising at home, learn new stuff or just practice your instrument. It’s also a great tool for teachers.

🎷 JJazzLab is designed to make non-boring backing tracks, backing tracks with variety, rhythmic accents and dynamics. You can start a solo slowly and gradually build up the atmosphere!

💻 Thanks to the underlying JJazzLab-X open-source platform developers can easily add new features and new music generation capabilities.

## Features

### Backing tracks

* Instant generation of a Midi backing track with drums, percussion, bass, piano, guitar, pad, horn section, …
* Fine tuning of the backing track per song part: rhythm variation, intensity, muted instruments, drum fills, tempo factor, custom phrases, drums transform…
* Play from anywhere, loop selected bars
* Play transposed (e.g. for sax or trumpet players)
* Any song structure: intro, chorus, 1st coda, etc.
* Adjust tempo, transposition, choose and solo/mute instruments
* Import user tracks
* Support for multi-rhythm backing tracks, possibly with different time signatures
* Export to Midi file, the full backing track or a single instrument track
* Easy Midi-to-MP3 conversion via export to Midi file
* Customizable click and pre-count

### Editors

* Chord lead sheet editor, song structure editor, chord symbol editor, mix console, song memo editor
* Multi-file editor with dockable windows
* Intuitive user interface with unlimited undo/redo, copy/paste between songs
* Free placement of the chord symbols (quantified or not), off-beat chord symbols anticipation
* Support all pop-rock and jazz chord symbols, plus user-defined chord symbols
* Edit chord symbol musical rendering: underlying harmony, accent type, harmony variation during solos, chord symbol substitution, …
* Drag & drop support to import/export Midi files
* Customizable song template
* Customizable UI colors and fonts
* Print chord lead sheet and song structure

### Rhythms

* Support for Yamaha style files (SFF1 & SFF2 format), access to thousands of free styles on the web
* Hundreds of embedded rhythms in the installer
* Support for “YamJJazz Extended Yamaha" style files for even more variations per style
* Open architecture: new rhythm generation engines can be easily added via plugins

### Notes viewer

* Show backing track notes in real time
* Show selected chord symbol notes and scales
* Piano keyboard
* Guitar diagrams with most common chords, open/close voiced chords, inversions

### (pseudo) Arranger keyboard mode

* Recognize chords played on Midi IN and update the backing track in (pseudo) real-time

### Improvisation help

* Automatic generate improvisation guides on your chord leadsheet&#x20;
* Based on Hal Crook's reference book "How to improvise"

### Midi

* Connect to any audio engine via Midi: SoundFont player (recommended with the JJazzLab SoundFont), Java internal synth, external synth, VST host via virtual Midi port such as ‘LoopBe1’
* Compatible with GM/GM2/XG/GS instruments
* Compatible with any Midi instrument via Cakewalk instrument definition files (.ins)
* Automatic drums/percussion drum map remapping from Yamaha XG key map to GM/GM2/GS key maps
* Optimized JJazzLab SoundFont for a high-quality rendering and automatic instrument selection
* Ready-to-use presets for VirtualMidiSynth (Windows) and FluidSynth (Linux)
* User-defined default mix per rhythm
* User-defined default instruments

### Import

* Band-In-A-Box lead sheet files
* musicXML lead sheet files
* Impro-Visor lead sheet files

### Miscellaneous

* Song memo with hyperlinks opened upon song loading
* Easily add new features thanks to the open-source pluggable architecture
* Based on the Netbeans application framework
