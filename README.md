# Blocky — Stack & Smile! 🧱

A colorful, privacy-first block-stacking game built as an installable Progressive Web App (PWA).
Made by **BKAOS**.

**[▶️ Play it live](#)** — *(add your GitHub Pages link here once deployed)*

## What it is

A Tetris-style stacker with:
- 7 hand-tuned color palettes (Rainbow Pop, Candy Land, Ocean Splash, Jungle Fun, Midnight Magic,
  Punk Rock, Bedtime Glow), each with matching sky/panel theming and decorations
- "Shape KAOS" difficulty decks — swap in smaller (3-block) or larger (5-block/pentomino) pieces
  alongside the classic 4-block tetrominoes
- Full accessibility panel: colorblind-safe palette, high contrast, reduce motion, large UI text,
  sound and haptics toggles — all independently switchable
- Touch controls built for mobile: drag to move, tap left/right to rotate, swipe down to hard-drop,
  plus full keyboard support for desktop testing
- Local high scores, no accounts, no leaderboard servers

## Why it's built this way

This is a BKAOS project, which means a few things are non-negotiable:
- **Zero network calls.** No analytics, no ad SDKs, no font CDNs, no accounts. Everything — scores,
  settings, palette choice — lives in `localStorage` on your device and nowhere else.
- **Installable, not app-store-gated.** It's a PWA: open the link, "Add to Home Screen" on iOS or
  Android, and it runs full-screen like a native app, offline, with its own icon. No developer
  account required to try it.
- **Accessibility isn't an afterthought.** The accessibility panel isn't a checkbox for compliance —
  colorblind-safe palettes and high-contrast mode use real research (Okabe-Ito palette), and every
  toggle is independently testable.

## Tech stack

Vanilla HTML/CSS/JS, `<canvas>` for rendering, Web Audio API for sound, the Vibration API for
haptics, and a hand-written service worker for offline caching — no frameworks, no build step,
no dependencies. That's a deliberate choice: it keeps the whole app auditable in one read-through
and deployable by just pushing static files.

## Running it locally

```bash
# any static file server works, e.g.:
npx serve .
# then open the printed localhost URL
```
Opening `index.html` directly via `file://` also works for gameplay, but the service worker
(offline support / installability) requires being served over `http(s)://` — that's a browser
security rule, not a bug here.

## Deploying (GitHub Pages)

1. Push this folder to a GitHub repo.
2. Repo Settings → Pages → deploy from the `main` branch, root folder.
3. Your live URL will be `https://<username>.github.io/<repo>/`.
4. Visit it on your phone → browser menu → "Add to Home Screen".

## What I learned building this

- Structuring an app so accessibility settings (contrast, motion, text size, colorblind palettes)
  apply globally via a single `Settings` object and CSS custom properties, rather than sprinkling
  conditionals through every render function.
- Building touch controls that distinguish a tap (rotate) from a drag (move) from a hold (soft-drop)
  from a swipe (hard-drop) using timing + distance thresholds on raw pointer events.
- Converting a single-file app into an installable PWA: manifest, icons (including maskable
  variants for Android's adaptive icon shapes), and a cache-first service worker.
- Enforcing a "zero network calls" constraint by catching and removing an external font CDN
  dependency that had quietly snuck in during earlier development.

## Project status

See `FUTURE_IDEAS.md` for parked feature ideas. This build is intentionally scoped to be
**finished** — playable, installable, documented — before anything new gets added.

---
*Blocky is made by BKAOS.*
