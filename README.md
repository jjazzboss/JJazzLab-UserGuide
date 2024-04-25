---
description: A complete and open application for backing tracks generation.
---

# JJazzLab 4

{% hint style="info" %}
Want to add or fix documentation? Yes you can!😀 Visit the [Improve documentation](contribute/improve-doc.md) page.
{% endhint %}

![JJazzlab 4](.gitbook/assets/JJazzLab4-full1.png)

## Where to start?

Try this very short [video tutorial](video-tutorials.md#for-starters).

## What is JJazzLab?

🎵 JJazzLab is a desktop application which automatically generates backing tracks for any song, even complex ones. It’s a jam buddy to have fun improvising at home, learn new stuff or just practice your instrument. It’s also a great tool for teachers.

🎷 JJazzLab is designed to make non-boring backing tracks, backing tracks with variety, rhythmic accents and dynamics. You can start a solo slowly and gradually build up the atmosphere!

💻 JJazzLab is open-source:  developers can easily add new features and new music generation capabilities.

## Features

### Backing tracks

* Instant generation of a Midi backing track with drums, percussion, bass, piano, guitar, pad, horn section, …
* Fine tuning of the backing track per song part: rhythm variation, intensity, muted instruments, drum fills, tempo factor, custom phrases, drums transform, …
* Add user tracks, which can also be used to change predefined rhythm tracks
* Play from anywhere, loop selected bars
* Play transposed (e.g. for sax or trumpet players)
* Any song structure: intro, chorus, 1st coda, etc.
* Adjust tempo, transposition, choose and solo/mute instruments
* Support for multi-rhythm backing tracks, possibly with different time signatures
* Export to Midi or MP3/Wav file, the full backing track or a single instrument track
* Customizable click and pre-count

### Editors

* Chord lead sheet editor, song structure editor, chord symbol editor, mix console, notes editor, song memo editor
* Multi-file editor with dockable windows
* Intuitive user interface with unlimited undo/redo, copy/paste between songs
* Free placement of the chord symbols (quantified or not), off-beat chord symbols anticipation
* Support all pop-rock and jazz chord symbols, plus user-defined chord symbols
* Edit chord symbol musical rendering: underlying harmony, accent type, harmony variation during solos, chord symbol substitution, …
* Add annotations or lyrics to measures
* Drag & drop support to import/export Midi files
* Customizable song template
* Customizable colors and fonts
* Print chord lead sheet and song structure

### Rhythms (styles)

* Support for Yamaha style files (SFF1 & SFF2 format), access to thousands of free styles on the web
* Hundreds of embedded rhythms in the installer
* Support for “YamJJazz Extended Yamaha" style files for even more variations per style
* Open architecture: new rhythm generation engines can be easily added via plugins

### Easy reader window

* Show the currently playing chords and annotations/lyrics

### Notes viewer

* Show selected chord symbol notes and scales with piano keyboard, guitar diagrams or score&#x20;

### (pseudo) Arranger keyboard mode

* Recognize chords played on Midi IN and update the backing track in (pseudo) real-time

### Improvisation help

* Automatic generate improvisation guides on your chord leadsheet
* Based on Hal Crook's reference book "How to improvise"

### FluidSynth, the JJazzLab builtin synth

* JJazzLab embeds a ready-to-use synth based on FluidSynth, with good sounds optimized for JJazzLab

### Midi

* If not using FluidSynth, you still can connect JJazzLab to a Midi synth (hardware or software) with advanced configuration possibilities

### Import

* Band-In-A-Box / MusicXML / Impro-Visor lead sheet files
* Import .txt files or copy/paste text like "|A7 D7 | Gm7 C7|"

### Miscellaneous

* Song memo with hyperlinks opened upon song loading
* Easily add new features thanks to the open-source pluggable architecture
* Based on the Netbeans application framework
