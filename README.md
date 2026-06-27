<div align="center">

# 🍓 Strawbooth

**a cute lil camera for the girlies — cottagecore digicam vibes, no upload, no tracking, just vibes**

![vanilla js](https://img.shields.io/badge/built%20with-vanilla%20JS-FFD7E2?style=flat-square)
![no frameworks](https://img.shields.io/badge/frameworks-none-7C9473?style=flat-square)
![runs offline](https://img.shields.io/badge/runs-fully%20offline-E3445C?style=flat-square)

</div>

---

## ✨ what it does

Strawbooth is a single-file web photobooth that turns your camera (or a photo from your gallery) into a little keepsake — either a classic **4-shot photo strip** or a **polaroid**, dressed up with strawberry milk / disposable cam / matcha cream filters and a Y2K-digicam HUD.

- 🍓 **strawberry-shaped shutter button** — leaves, seeds, the whole thing, built in pure CSS
- 🎞️ **strip mode** (4 shots) or **📸 polaroid mode** (1 shot), your pick
- 🍓🍃🌸 **3 film filters**: strawberry milk, disposable cam, matcha cream — plus a clean no-filter option
- 📼 **digicam HUD**: blinking REC dot, live `YYYY.MM.DD HH:MM` timestamp in a pixel LCD font, shot counter, strawberry corner markers
- 📸 countdown + camera flash + a tiny synthesized shutter click before every shot
- 🧁 final photo is composited on canvas with a gingham background, rounded photo frames, a random handwritten caption, and corner stickers — then downloads as one PNG
- 🔄 flip-camera button (front/back) + auto-mirrored selfie preview
- 🖼️ **automatic gallery fallback** — if camera access is blocked, it quietly switches to "choose photo" so it never just breaks
- 🔒 **100% client-side.** no server, no analytics, no network calls. nothing you photograph ever leaves your browser

## 🛠️ tech stack

just three files' worth of vanilla web tech, all in one HTML file:

- **HTML/CSS** — layout, the strawberry shutter button, the digicam HUD
- **JavaScript** — `getUserMedia` for the camera, `<canvas>` for capturing + compositing + filters/grain/vignette, Web Audio API for the shutter click
- **Google Fonts** — Chewy (logo), Quicksand (UI), Caveat (handwritten captions), VT323 (digicam timestamp)

No build step, no `node_modules`, no dependencies to install.

## 🚀 getting started

### run it locally
```bash
git clone https://github.com/strawbkvma/strawbooth.git
cd strawbooth
```
Then just open `strawbooth.html` in your browser — double-click it, or:
```bash
# optional: serve it so camera permissions behave nicely on some browsers
npx serve .
```

### deploy it (GitHub Pages)
Or you can click [here](https://strawbkvma.github.io/strawbooth/) to try it! 🍓

> camera access requires **https** or **localhost** in most browsers — both GitHub Pages and `npx serve` cover that.

## 🎨 customizing

everything lives in `strawbooth.html`, no separate config file:

| want to change... | edit this |
|---|---|
| color palette | the CSS variables at the top of `<style>` (`--strawberry`, `--leaf`, `--cream`, etc.) |
| filters | the `FILTERS` object in the `<script>` — add a new key with a `css` filter string + optional `tint` / `grain` / `vignette` |
| captions | the `CAPTIONS` array |
| photo resolution | `targetW` / `targetH` inside `captureFrameFromVideo()` |
| strip length | `state.shotsNeeded` set in the mode-toggle handler |

## 📝 notes

- works best on a real device/browser — some sandboxed previews block camera access, in which case it falls back to picking a photo instead
- tested with the front + back camera on mobile and webcams on desktop
- if a filter looks off on your screen, it's probably your monitor's color profile being dramatic, not the code lol

## 💌 credits

made with 🍓 by Nana / Strawbkvma — part of the *strawberry* series of kawaii web mini-projects.

<div align="center">

made with 🍓 for the girlies

</div>
