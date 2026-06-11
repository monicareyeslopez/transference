# Transference Coder

A self-contained qualitative coding application for labeling transference patterns in AI companion community posts. Built for a study analyzing 1,000 Reddit posts across r/replika, r/KindroidAI, r/CharacterAI, r/therapyGPT, and r/MyBoyfriendIsAI.

No installation, no server, no dependencies. Everything runs in a single HTML file in your browser.

## Usage

1. Download `transference_coder.html`
2. Open it in Chrome
3. Upload your CSV file
4. Code away — progress autosaves to your browser's local storage
5. Export your CSV at the end of each session to save your work to disk

## Features

- **Guided 7-step coding flow** — steps activate, dim, or mark as N/A based on prior answers
- **Keyboard shortcuts** — numpad-mapped for high-volume coding efficiency
- **Jump to index** — navigate directly to any row by number
- **Text highlighting** — select and annotate passages in post text; exports to CSV
- **Ambiguous case flagging** — flag uncertain posts; exports as a binary `ambiguous` column
- **Overview & charts** — live transference rates, type distribution, valence and intention breakdowns
- **Coder notes search** — search across all your notes entries
- **Research memo pad** — free-form scratch pad for cross-dataset observations
- **Text-to-speech** — read posts aloud with adjustable speed
- **Session timer & streak counter** — track momentum across long coding sessions
- **Autosave** — progress saved to localStorage continuously; restored on re-upload
- **Round-trip CSV** — exported CSV preserves highlights and flags for the next session

## Coding Schema

Posts are coded across seven steps:

| Step | Field | Notes |
|------|-------|-------|
| 1 | `self_disclosure` | Present in all posts |
| 2 | `manual_label_transference` | SD=1 only |
| 3 | `transference_valence` | T=1 only |
| 4 | `post_intention` | SD=1 only |
| 5 | Metadata | Age, gender, relationship status, alt tool |
| 6 | Transference types | T=1 only |
| 7 | `manual_coder_notes` | Required if type_other=1 |

Media coding and the `ambiguous` flag apply to all posts.

## Requirements

- Google Chrome (recommended for text-to-speech support)
- A CSV file matching the expected 34-column schema

## Notes

All data stays in your browser. Nothing is uploaded anywhere.
