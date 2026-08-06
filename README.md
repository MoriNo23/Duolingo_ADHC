# Duolingo ADHC — Progress bar milestones (for the easily distracted / bored)

<div align="center">

![License](https://img.shields.io/badge/license-MIT-blue)
![Tampermonkey](https://img.shields.io/badge/tampermonkey-userscript-green)
![Version](https://img.shields.io/badge/version-1.5.3-orange)

</div>

## Install

- **Greasy Fork:** https://greasyfork.org/es-419/scripts/590127-duolingo-adhc-progress-bar-milestones-for-the-easily-distracted-bored
- **Manual:** install `duolingo-adhc.user.js` in Tampermonkey / Violentmonkey / Greasemonkey.

## What it does

Adds rarity-based milestone overlays on Duolingo lesson progress bars (wood → bronze → silver → gold → platinum → legendary), with particle burst on milestone cross and a theme-aware settings panel in EN/ES.

- Targets only lesson progressbar (not `/learn` challenge bar).
- Preserves Duolingo native design (Feather Design System).
- Settings panel lets you change milestones count, show/hide numbers, thickness, and language.

## Preview

`uiAni.webm` shows the bar animating from 0% → 100% (recorded with Spectacle).

## Workflow for screenshots / video

- Open `showcase.html` locally.
- Capture PNGs manually with Spectacle.
- For video: use the animation harness + Spectacle recording; convert to GIF locally with ffmpeg if needed.

## Roadmap

- Shine animation polish + pause on tab blur.
- `findBar()` fallback selector for class changes.
- Future: per-device config export/import, compact mode, animation toggle.

## License

MIT — see `LICENSE`.
