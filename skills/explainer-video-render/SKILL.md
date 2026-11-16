---
name: explainer-video-render
description: >-
  Use when making a short product explainer video from code: an HTML/GSAP scene
  seeked frame by frame in headless Chromium, rendered to PNG frames, then muxed
  with music and UI click sounds into an MP4 with ffmpeg.
---
# Explainer video: scene → frames → mp4

Deterministic, code-only motion. No screen recording, no real-time capture: every frame is a seek, so renders are identical every run.

## Folder layout (one folder per video, e.g. `videos/<slug>/`)
- `scene.html` — the animated scene (one per cut; variants like `scene-minimal.html` are fine)
- `render.mjs` — the renderer (stills mode by default, `--full` for the mp4)
- `fonts/` — local `.woff2` files referenced with `@font-face` and `font-display: block` (never a CDN font)
- `audio/bed.mp3` — the music bed (only with a licence you can show)
- `stills/` — review stills, committed
- `out/<slug>.mp4` — the finished cut
- Frames go to a temp dir (`/tmp/<slug>-frames`), never committed.

## 1. The scene contract
`scene.html` is a static page that animates nothing on its own. It must expose:
- `window.DURATION` — length in seconds
- `window.CLICKS` — `{ name: seconds }` for every on-screen tap, used for the click sounds
- `window.seek(t)` — puts the page in its exact state at time `t` (GSAP: `tl.seek(t, true)` on a paused timeline)
- `window.ready = true` — set only after `document.fonts.ready` resolves and the timeline is built
- optional `?t=<seconds>` query to open at a time, for quick checks

Build with a single paused GSAP timeline (`gsap.timeline({ paused: true })`), absolute times, and small helpers (`move` the cursor, `hover`, `press` at `CLICKS.x`, `morph` between screens). End with `tl.set({}, {}, DURATION)` so the timeline length is exact. Use `immediateRender: false` on `fromTo` steps that start later. No `Date.now()`, `Math.random()` without a seed, CSS transitions, or video elements, since they break seeking.

Use fake, clearly synthetic data in every scene (names, numbers, health values). Never real user data.

## 2. Stills first (always)
Run `node render.mjs` with no flag:
- launch Playwright Chromium headless, viewport at half the target size with `deviceScaleFactor: 2` (e.g. 960×600 → 1920×1200, 720×720 → 1440×1440)
- `goto` the file URL, `waitForFunction(() => window.ready === true)`, check `document.fonts.check("500 64px <Font>")` is true
- seek to each key moment (every click, every screen change, start and end) and screenshot into `stills/t-<time>.png`

Look at the stills before rendering. Fix layout, text, fonts and timing here; it's seconds instead of minutes.

## 3. Full render (`--full`)
- Frames: for `i` in `0 … DURATION*fps`, `seek(i/fps)` then `screenshot` to `f%05d.png`. 60 fps is the default.
- Motion blur (optional): render at `60*4` fps and blend with `tmix=frames=4:weights='1 1 1 1',fps=60`.
- Audio: trim the bed to the cut, `atrim=start=<offset>:duration=<DURATION>,asetpts=PTS-STARTPTS`, fade in 0.05 s and out over the last 2 s, `volume=0.8`. Use `atempo` only to fit a tempo on purpose.
- Clicks: one synthesized tick per `CLICKS` entry, `-f lavfi -t 0.06 -i aevalsrc=0.18*sin(2*PI*2600*t)*exp(-t*110)|…:s=48000`, `adelay` to its time in ms, then `amix=inputs=N:normalize=0` with the bed.
- Encode: `-c:v libx264 -pix_fmt yuv420p -crf 16 -preset slow -c:a aac -b:a 192k -t <DURATION> -movflags +faststart`.
- Delete the temp frames dir afterwards.

Get ffmpeg from `ffmpeg-static` and Playwright from the repo's own `package.json` (pinned), never hard-coded `node_modules/.pnpm` paths. Install Chromium with `npx playwright install chromium`.

## 4. Prove it
Before calling a cut done, report:
- `ffprobe` output: duration matches `DURATION` ±1 frame, resolution, 60 fps, h264 + aac
- 3–5 stills from the final mp4 (`ffmpeg -ss <t> -frames:v 1`) at the key clicks
- fonts loaded (`fontReady: true`), no console errors from the page
- render time and file size

## Rules
- One video per folder; one scene per cut; keep scenes self-contained (inline CSS, local fonts, local GSAP copy or a pinned npm import).
- Brand, colors, fonts and copy come from the product's own design source, never from another product's scenes.
- No medical, financial or performance claims in on-screen copy unless the product owner supplied them.
- Commit stills and the final mp4; never commit raw frames.
