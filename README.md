# Cabin Games

Family card game scorekeeper — installable PWA (no App Store needed).

**Live URL:** https://mskluz763.github.io/cabin-games/

---

## Installing on a phone

1. Open the URL above in the phone's browser
2. **iPhone (Safari):** tap the Share icon → "Add to Home Screen"
3. **Android (Chrome):** tap the install banner or the three-dot menu → "Add to Home Screen"

The app works offline once installed.

---

## Games included

| Game | Players | Goal |
|---|---|---|
| Five Crowns | 2–8 | 11 rounds, lowest score wins |
| Hearts | 2–6 | Avoid points, shoot the moon |
| MN Canasta | 2–4 (or 4-player partners) | First to 20,000 pts |
| Euchre | 4 (2 partnerships) | First to X games won |
| 500 | 4 (2 partnerships) | First to 500 pts, includes Noula |

---

## File structure

```
pwa/
  index.html          — home screen / game hub
  manifest.json       — PWA name, icons, display settings
  sw.js               — service worker (offline/cache support)
  icons/
    icon.svg
    icon-maskable.svg
  five-crowns/index.html
  hearts/index.html
  canasta/index.html
  euchre/index.html
  500/index.html
```

---

## Making changes

Edit any file in the `pwa/` folder, then run these three commands from inside the `pwa/` folder to publish:

```
git add .
git commit -m "describe what you changed"
git push
```

The site updates within a minute. Refresh the browser to see changes.

---

## Adding a new game

1. Create a new folder under `pwa/` (e.g. `pwa/newgame/index.html`)
2. Follow the dark-navy theme (see Theme section below)
3. Add a back button linking to `../index.html`
4. Add a card to `pwa/index.html` pointing to the new folder
5. Add the new file path to the `ASSETS` array in `pwa/sw.js` so it works offline
6. Push with the commands above

---

## Theme tokens

| Token | Value | Used for |
|---|---|---|
| Background | `#060d1f` | Page background |
| Surface | `#0b1630` | Cards / panels |
| Border | `#1e3a6e` | Card borders |
| Text | `#d6e8ff` | Primary text |
| Muted | `#6a90c0` | Subtitles, descriptions |
| Accent | `#7eb8f7` | Highlights, links |
| Red suits | `#c24040` / `#e8445a` | Hearts, diamonds |
| Fonts | Cinzel (headings) + Crimson Pro (body) | Google Fonts |

---

## How GitHub Pages works

The `main` branch of this repo is automatically served at the live URL above. Every `git push` triggers a redeploy (takes ~1 minute). No build step needed — it's all plain HTML/CSS/JS.
