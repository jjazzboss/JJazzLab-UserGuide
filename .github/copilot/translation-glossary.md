# JJazzLab translation glossary

This file is the reviewable terminology source for the manual translation workflow in `.github/workflows/manual-translation-sync.yml`.

Rules:
- Every term listed here must stay in English in all translation branches.
- Use the **Notes** column to capture meaning or branch-specific guidance before running the workflow.

| English term | Notes |
| --- | --- |
| JJazzLab | Product name |
| song | The main model object saved as .sng file, contains a lead sheet, a song structure and possibly user tracks |
| user track | A user-generated musical phrase for a song |
| lead sheet | Contains chord symbols and possibly bar annotations grouped in sections.|
| section | Labels like A, B, verse, chorus in the chord lead sheet |
| chord symbol | Same as chord |
| bar annotation | Text associated to a bar |
| song structure | Contains the song parts which define in which order sections are played and how |
| song part | Associated to a parent section, defines a rhythm and its rhythm parameters ||
| rhythm | In this guide means a music style (rock, bossa-nova, ...) rather than only rhythm in the musical-theory sense |
| rhythm engine | A music generation engine which provides rhythm instances. Same as rhythm provider. |
| rhythm parameter | Variation, Intensity, Fill are examples |
| song mix | Defines the MIDI instrument and MIDI settings for each channel used by the song |
| mix console | Editor for the song mix|
| song structure editor | Editor for song structure |
| lead sheet editor | Editor for lead sheet |
| song part editor | Editor for song part |
| notes editor | Editor of a musical phrase at note level |
| File/Import Songs... | Example of literal UI/menu string |
| output synth | Represents the capabilities of the MIDI synth connected to JJazzLab |
| FluidSynth | A pre-configured FluidSynth instance used as output synth |
| YamJJazz | Rhythm engine name. Uses Yamaha style files. |
| jjSwing | Rhythm engine name. Also a rhythm name. Optimized for swing jazz music |


## Review notes

- Add or adjust rows here whenever you notice repeated terminology drifting across languages.
- Remove a term from this file only if you explicitly want to allow it to be translated.
