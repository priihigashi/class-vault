# Class Vault

One phone-sized page listing every class Priscila has bought, with the login each one needs.
Built to live on the iPhone home screen.

**Live:** https://priihigashi.github.io/class-vault/
(this repository has GitHub Pages serving from `main` / root.)
private, and Pages on a private repo needs a paid plan — so the published copy lives there and
this folder is the source of record.)

## Files

| File | Role |
|---|---|
| `index.html` | The whole page. Self-contained, no build step, no dependencies. |
| `sw.js` | Service worker. Caches the shell so it opens with no signal. Bump `CACHE` to ship an update. |
| `manifest.webmanifest` | Makes "Add to Home Screen" launch it standalone as **Classes**. |
| `favicon.svg` | Browser tab — the brand orbit on graphite. |
| `apple-touch-icon.png` | 180×180 home-screen icon, generated to match the in-page brand mark. |

## Design

Not a new look — this reuses her own Liquid Glass system, lifted from
`adhd-focus-coach @ finish-pass-liquid-glass-2026-08-24`:

- Tokens from `frontend/src/index.css`: `--hot-pink #eb4f9b`, `--lilac #c9a7ef`, `--coral #f27d68`,
  `--peach #ffb879`, `--cream #fff7ee`, `--graphite #171318`, `--glass-fill`, `--glass-shadow`.
- Primitives from `frontend/src/App.css`: `.glass-card`, `.glass-pill`, `.metric-chip`,
  `.focus-ring` (conic progress), `.primary-gloss` (the CTA gradient), `.hero-bloom`.
- Type pairing from the same source: **Fraunces** for headings, **DM Sans** for body.
- Focus ring `3px rgba(235,79,155,.48)` at `3px` offset, as in her `index.css`.

Dark theme is derived from the same tokens with `--cream` inverted to graphite.

## Where the data came from

| Source | What it gave |
|---|---|
| [Learning Library — Master Course Tracker](https://docs.google.com/spreadsheets/d/1IQ66TKQV_YL1qyJ-zvrNZrO8hBOFJ5Zgt_DlzUjhusg/edit) | 15 of the 16 rows, including the Hotmart audit of the Hotmail inbox |
| Gmail, `noreply@cameronacademy.com`, 10 Sep 2026 | The newest purchase, its username, course URL, and the outstanding registration form |
| Drive doc "ticktick" | The note `NEXT CLASS $37 aipapito`, which identified AI Papito |

The seven Hotmart rows are transcribed from the tracker's earlier audit of
the Hotmail account, which is not a connected mailbox — they were **not** re-verified
against Hotmart directly.

## Updating it

Edit `index.html` and push to `main`; Pages redeploys on its own. Bump `CACHE` in `sw.js` in the
same commit, or returning visitors keep the cached copy.
