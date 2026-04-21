# Voice Rabbit — UI Reference

Design reference for the Voice Rabbit macOS app. No build step — open any HTML file directly in a browser.

---

## Files

### `app-home.html`
The full Mac app UI prototype. Includes all screens:
- **Home** — transcription history with copy/delete
- **Dictionary** — custom word list with add/edit/delete
- **Style** — writing style selector (Concise, Balanced, Detailed)
- **Settings** — keyboard shortcuts, microphone picker, language
- **Support** — modal overlay

Built with React 18 (loaded from CDN via Babel standalone). No server needed — just open the file.

### `recording-pill-demo.html`
Isolated reference for the recording pill that appears when the user is dictating. Shows both modes:
- **Push to talk** — no stop button, pill disappears on hotkey release
- **Hands-free** — cream stop button, stays on screen until dismissed

Includes a live demo with real mic input (Web Audio API). If mic permission is denied, falls back to CSS animation. This file is for developer reference only — the pill is not part of `app-home.html`.

### `assets/`
- `rabbit-logo.svg` — the full Voice Rabbit logo (used in app sidebar)
- `rabbit-logo.png` — PNG version

---

## Design Tokens

Key CSS variables used throughout the app:

| Variable | Value | Usage |
|---|---|---|
| `--bg` | `#f8f5ef` | Page background |
| `--surface` | `#ffffff` | Cards, modals |
| `--ink` | `#18150f` | Primary text |
| `--accent` | `#d4a043` | Highlights, active states |
| `--sans` | Inter | Body font |
| `--display` | Fraunces | Logo, headings |

---

## Recording Pill Spec

The pill sits centered at the bottom of the screen, fixed position.

| Property | Value |
|---|---|
| Background | `#1a1d24` |
| Border radius | `9999px` (true capsule) |
| Padding | `10px 16px 10px 13px` |
| Icon | Rabbit SVG, 24x24, white |
| Bars | 18 bars, 2px wide, `#f0ebe0`, animated via CSS |
| Entrance | 200ms spring ease, fade + translateY + scale |

**Push to talk:** no stop button. Dismiss on hotkey release.

**Hands-free:** cream circular stop button (22x22px). Dismiss on stop button tap or second hotkey press.

---

## Fonts

Both files load from Google Fonts — requires an internet connection to render correctly.

- [Inter](https://fonts.google.com/specimen/Inter) — UI text
- [Fraunces](https://fonts.google.com/specimen/Fraunces) — logo and display (app-home only)
