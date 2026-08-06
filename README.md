# Transference Coder

A self-contained qualitative coding application for labeling transference patterns in AI companion community posts. Built for a study analyzing Reddit posts across r/replika, r/KindroidAI, r/CharacterAI, r/therapyGPT, and r/MyBoyfriendIsAI.

No installation, no server, no build step. The whole app is one HTML file (`index.html`) — everything runs in your browser, and it's hosted live via GitHub Pages at [monicareyeslopez.github.io/transference](https://monicareyeslopez.github.io/transference/).

## Usage

1. Open the [live app](https://monicareyeslopez.github.io/transference/) (or download `index.html` and open it locally).
2. Click **Load from Google Sheets** and sign in — this is the primary workflow. Everything you code saves straight back to the connected sheet, so there's nothing to remember at the end of a session; just close the tab and pick up where you left off next time.
3. A CSV upload is also available (drag-and-drop or "Upload a CSV instead") if you'd rather work from a file. Progress on a CSV session autosaves to your browser's local storage, and can be exported back to CSV at any time.
4. Code away. On mobile, the app installs like a native app — see below.

### Installing on mobile

The app is an installable PWA (Progressive Web App):

- **iPhone**: open the link in **Safari**, tap the Share icon, then **Add to Home Screen**.
- **Android**: open the link in **Chrome**, tap the **⋮** menu, then **Add to Home screen** / **Install app**.

Once installed it launches full-screen with its own icon, and the app shell is cached for offline loading.

## Features

- **Guided coding flow** — steps activate, dim, or mark as N/A based on prior answers; on mobile this is a one-question-at-a-time step carousel with swipe/arrow navigation that loops back to step 1 after the last step
- **Google Sheets sync** — primary save/load path, with autosave debouncing, retry-on-token-expiry, and an offline queue that flushes once reconnected
- **Media coding presets** — one-tap fills for recurring patterns (romantic chat screenshot, AI avatar display, love song), each prompting for the media count and then stepping through the rest of the (pre-filled) attributes
- **Keyboard shortcuts** — numpad-mapped for high-volume coding efficiency (desktop)
- **Jump to index / jump to next uncoded** — navigate directly to any row, or skip straight to the next (or previous) uncoded post
- **Text highlighting** — select and annotate passages in post text; exports to CSV
- **Ambiguous case flagging & consistency warnings** — flag uncertain posts, and get warned before saving if required fields are missing or inconsistent
- **Overview & charts** — live transference rates, type distribution, valence and intention breakdowns, plus a reading-time-remaining estimate across the whole dataset
- **Coder notes search** — search across all your notes entries
- **Research memo pad** — free-form scratch pad for cross-dataset observations
- **Text-to-speech** — read posts aloud with an adjustable speed dropdown (1.0×–2.5×); keeps speaking in the background on supported browsers (e.g. when you tap out to check the Reddit link)
- **Session timer & streak counter** — track momentum across long coding sessions
- **Round-trip CSV** — exported CSV preserves highlights and flags for the next session

## Coding Schema

Posts are coded across four top-level steps, two of which branch into sub-steps:

| Step | Field | Notes |
|------|-------|-------|
| 1 | Metadata | Age, gender, relationship status, alt tool — present in all posts |
| 2 | Media coding | Present in all posts |
| 3 | `self_disclosure` | Present in all posts |
| 3.1 | `post_intention` | SD=1 only |
| 3.2 | `manual_label_transference` | SD=1 only |
| 3.2.1 | `transference_valence` | T=1 only |
| 3.2.2 | Transference types | T=1 only |
| 4 | `manual_coder_notes` | Required if type_other=1 |

The `ambiguous` flag applies to all posts.

## Requirements

- A modern browser (Chrome recommended for the best text-to-speech support)
- Either a Google account with access to the connected coding sheet, or a CSV file matching the expected column schema

## Notes

All data stays in your browser and your connected Google Sheet — nothing else is uploaded anywhere.
