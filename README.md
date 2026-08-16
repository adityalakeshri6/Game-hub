
# Aditya's Game Hub

A small collection of free browser games, bundled as an installable web app
(PWA) - no app store, no download, works offline after the first visit.

## Play it

Open `index.html` (or the live GitHub Pages link) and pick a game:

- **Tic-Tac-Toe** - play against an unbeatable minimax AI
- **Number Puzzle X** - a colorful 2048-style number merging game with
  sound, combos, difficulty modes, and score sharing

## Installing as an app

On Android (Chrome): open the site, then either tap the "Add to Home
Screen" button on the hub page, or use the browser's own menu -> "Add to
Home screen" / "Install app". It'll then open full-screen from your home
screen icon, just like a regular app.

## Files

```
game-hub/
├── index.html              -> hub / landing page linking to both games
├── manifest.json           -> PWA config (name, icons, colors)
├── sw.js                   -> service worker, caches files for offline use
├── icons/
│   ├── icon-192.png
│   └── icon-512.png
├── tic-tac-toe/
│   └── index.html
└── number-puzzle/
    └── index.html
```

Each game is fully self-contained in its own folder - the hub is just a
menu page linking to them, nothing shared between them at runtime.

## Notes

- The service worker caches the core pages on first visit, so the hub and
  both games keep working without a connection afterward. If you edit any
  game file later, bump `CACHE_NAME` in `sw.js` (e.g. `game-hub-v2`) so
  visitors actually get the update instead of a stale cached copy.
- Icons are simple generated placeholders - swap `icons/icon-192.png` and
  `icons/icon-512.png` for your own artwork any time, same file names.
