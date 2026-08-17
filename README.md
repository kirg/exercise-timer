# Exercise Timer - PWA

Installable PWA that works offline, suitable for GitHub Pages.

## GitHub Pages Deploy

Option 1: /docs folder
- Copy contents of this folder (`exercise-timer/`) into your repo's `docs/` folder
- GitHub Settings → Pages → Source: `Deploy from branch`, Branch: `main`, Folder: `/docs`
- Push. Your app will be at `https://<user>.github.io/<repo>/`

Option 2: root or gh-pages
- Copy files to repo root or to `gh-pages` branch root
- Enable Pages.

All paths are relative (`./`), so it works from subfolders.

## Files
- `index.html` - self-contained app (vanilla JS, inline CSS), registers SW, links manifest
- `manifest.json` - PWA manifest (name, short_name, standalone, icons)
- `sw.js` - service worker caching core for offline
- `icon-192.png`, `icon-512.png`, `apple-touch-icon.png`, `favicon.png`

## Features
- 27 exercises library + custom
- Routine builder: time/reps, rest, sets 1-10, weight kg, notes, skip toggle, dup/del, up/down reorder
- Weight memory via localStorage
- Player: circular progress, reps tap counter, rest distinct, progress bar, wake lock, audio beeps (Web Audio), 3-2-1 ticks, voice toggle
- History log + weight defaults editor
- Dark/light auto, mobile-first, big tap targets

## Local test
```
python3 -m http.server 8000
# open http://localhost:8000
# then check Application → Manifest in DevTools
# Lighthouse PWA should pass installable + offline
```

## Install
- Android Chrome: menu → Install app
- iOS Safari: Share → Add to Home Screen → launches standalone

No backend, 100% localStorage.
