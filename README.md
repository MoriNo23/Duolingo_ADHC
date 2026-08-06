# Duolingo ADHC — Progress bar milestones (for the easily distracted / bored)

<div align="center">

[![License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)
[![Tampermonkey](https://img.shields.io/badge/tampermonkey-userscript-green)](https://www.tampermonkey.net/)
[![Version](https://img.shields.io/badge/version-1.5.3-orange)](https://greasyfork.org/es-419/scripts/590127)
[![GreasyFork](https://img.shields.io/badge/Greasy%20Fork-Install%20Now-4ca64c)](https://greasyfork.org/es-419/scripts/590127-duolingo-adhc-progress-bar-milestones-for-the-easily-distracted-bored)

</div>

## Install

- **Greasy Fork**: https://greasyfork.org/es-419/scripts/590127-duolingo-adhc-progress-bar-milestones-for-the-easily-distracted-bored — click **Install** and confirm in your userscript manager.
- **Manual**: install `duolingo-adhc.user.js` in Tampermonkey / Violentmonkey / Greasemonkey.
- **Prerequisites**: a userscript manager extension. Refresh any open Duolingo lesson tab after installing.

## What it does

Turns the native Duolingo lesson progress bar into a **milestone-based reward system** with progressive material rarities:

| Tier | Rarity | Effect |
|------|--------|--------|
| 1 | 🪵 Wood | humble start |
| 2 | 🥉 Bronze | first milestone |
| 3 | 🥈 Silver | halfway |
| 4 | 🥇 Gold | victory near |
| 5 | 🩵 Platinum | high-tier milestone |
| 6 | 👑 Legendary | animated gradient + light sweeps + dynamic shines |

Crossing any milestone triggers a **particle burst** (color-matched to the tier). Reaching 100% unlocks a **massive celebratory explosion**.

- Targets **only the lesson progress bar** (not the `/learn` challenge bar).
- Preserves Duolingo's native Feather Design System (rounded pills, subtle shadows, auto light/dark mode).
- **In-app settings panel** (`⚙️` button): adjust milestones (1→12), toggle numbers, switch language (EN/ES).

## Preview

<video src="https://raw.githubusercontent.com/MoriNo23/Duolingo_ADHC/master/uiAni.webm"
       autoplay loop muted playsinline width="560">
</video>

`uiAni.webm` — bar animating from 0% → 100%, recorded with Spectacle.

## Screenshot Workflow

The repo keeps only production files. Local dev harnesses (`showcase.html`, `harness-state.html`) are used for inspection + manual captures:

1. Serve locally: `python3 -m http.server 8765` from the repo dir.
2. Open `http://localhost:8765/showcase.html`.
3. Capture each component manually with **Spectacle** (PNG for docs, WebM for motion).
4. For GIF: `ffmpeg -i input.webm -vf "fps=20,scale=560:-1:flags=lanczos,palettegen" palette.png && ffmpeg -i input.webm -i palette.png -filter_complex "fps=20,scale=560:-1:flags=lanczos[x];[x][1:v]paletteuse" output.gif`.

## Technical Notes

- `@name`/`@name:es` + `@description`/`@description:es` locales para Greasy Fork (English primary).
- CSS selectors target `.oCRF1`/`._3yKMC`/`._27NV6` (lesson bar) exclusively.
- `GM_addStyle` para inyección de capas de rareza/sweep/shines; `MutationObserver` sobre `aria-valuenow` para re-render.
- Sin dependencias externas en runtime (axe-core removido; fue dev-only).

## Roadmap

- Shine animation polish (sweep + fixed shines + flash) ✅ v1.4.9
- `findBar()` fallback selector for Duolingo class changes
- Per-device config export/import
- Compact mode + animation toggle

## License

MIT — see `LICENSE`.
