# JJazzLab User Guide repository instructions

## Build, test, and validation commands

- `lychee --verbose --no-progress "./**/*.md"` runs the same Markdown link validation used in `.github/workflows/link-checker.yml`.
- `lychee --verbose --no-progress "./path/to/file.md"` is the closest equivalent to a single-test run for this repo when you only changed one page.
- `workflow_dispatch` on `.github/workflows/manual-translation-sync.yml` is the manual translation workflow. It creates one issue per selected language and can assign the issue to Copilot cloud agent; `full_sync: true` creates bootstrap issues, while incremental runs use `from_ref`.
- There is no configured unit-test, lint, or real build pipeline in this repository. `pom.xml` must be ignored. Treat link checking as the authoritative automated validation.

## High-level architecture

- This repository is a GitBook-style content tree for the JJazzLab user guide, not the JJazzLab application code. `README.md` is the book home page, and `SUMMARY.md` defines the published sidebar/navigation structure.
- The published content is organized around the user journey and the app's main concepts: installation/getting started, sounds and MIDI setup, editors, songs, rhythms, tools, rhythm engines, and contribution pages.
- Translations are also managed as language-specific branches, not only as files in the current branch. Remote branches currently include `origin/french`, `origin/spanish`, `origin/japanese`, and `origin/german`.
- Several concepts span multiple sections and need consistent terminology:
  - **Song authoring flow:** the lead sheet defines chords, sections, and interpretation; the song structure arranges those sections into song parts and chooses rhythms/rhythm parameters; the mix console controls track-level sound settings; the note editor handles user tracks and custom phrases.
  - **Playback/rendering flow:** rhythm engines expose rhythm providers and rhythm parameters, while MIDI/output synth configuration determines how those generated parts are mapped to actual instruments and drum maps.
- Section landing pages may be `README.md` files inside directories, not only leaf `.md` files. For example, the root `README.md` and `rhythm-engines/yamjjazz-rhythm-engine/README.md` are both part of the published book.

## Key conventions

- Preserve the GitBook authoring syntax already used throughout the repo: YAML frontmatter such as `description:`, `{% hint %}` and `{% embed %}` blocks, HTML `<figure>` markup, and explicit anchors like `<a id="..."></a>`.
- When adding, renaming, or moving a published page, update `SUMMARY.md` in the same change. Prefer editing pages that are referenced from `SUMMARY.md` and current internal links.
- If a task involves translated documentation, check whether the change belongs on one of the language branches (`french`, `spanish`, `japanese`, `german`) rather than assuming translation content lives on `master`.
- The translation workflow uses `.github/copilot/translate-docs-prompt.txt` plus `.github/copilot/translation-glossary.md`; keep translation rules and shared terminology there instead of duplicating them inside multiple workflow steps or branches.
- Keep screenshots and other media under `.gitbook/assets` and reference them with relative paths.
- Use relative Markdown links with explicit `.md` targets and preserve anchors when editing section headings; the repo's automated validation checks links across all Markdown files.
- Use JJazzLab terminology consistently. In this guide, **rhythm** usually means a music style/backing style, and pages often rely on exact UI/menu wording such as `File/Import Songs...` or `Tools/Options/Midi`.
- Existing pages are user-facing documentation, so edits should preserve the current explanatory style: concrete workflows, exact feature names, and cross-links to related pages rather than code-centric implementation detail.
