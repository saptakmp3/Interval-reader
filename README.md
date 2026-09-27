# Interval Sight-Reader

A staff-based interval recognition trainer for sight-reading practice —
treble, bass, and mixed clef; melodic and stacked (harmonic) note display;
a points/streak/level system; and a timed speed-drill mode. Installable
as a phone app (PWA) — works offline once loaded.

## Deploy it on GitHub Pages (free, ~2 minutes)

1. Create a new **public** repo on GitHub (e.g. `interval-sight-reader`).
2. Upload every file in this folder to the repo root, keeping the
   `icons/` folder structure intact:
   ```
   index.html
   manifest.json
   service-worker.js
   icons/
     icon-16.png
     icon-32.png
     icon-152.png
     icon-180.png
     icon-192.png
     icon-192-maskable.png
     icon-512.png
     icon-512-maskable.png
   ```
   (Drag-and-drop into the GitHub web UI works fine — just make sure
   `icons/` uploads as a real folder, not flattened.)
3. Go to the repo's **Settings → Pages**.
4. Under "Build and deployment", set **Source: Deploy from a branch**,
   branch **main**, folder **/ (root)**. Save.
5. GitHub gives you a URL like:
   `https://<your-username>.github.io/interval-sight-reader/`
   It can take a minute or two to go live the first time.

## Install it on your phone

**iPhone (Safari):**
1. Open the GitHub Pages URL in Safari.
2. Tap the **Share** icon → **Add to Home Screen** → **Add**.

**Android (Chrome):**
1. Open the URL in Chrome.
2. Tap the **⋮** menu → **Add to home screen** (or **Install app**) → **Install**.

Once installed, it opens full-screen with its own icon — no address bar,
and it keeps working without an internet connection after the first load.

## Updating it later

If you come back and want changes (new features, tweaks, whatever):
1. Edit `index.html` (or ask Claude to and re-export it).
2. **Bump the cache name** in `service-worker.js` — change
   `interval-sight-reader-v1` to `-v2`, `-v3`, etc. — otherwise phones
   that already installed the app will keep serving the old cached
   version instead of picking up your changes.
3. Re-upload the changed files to the repo (or `git push` if you're
   using git locally). GitHub Pages redeploys automatically in a
   minute or so.

## Notes

- Your score, streak, best-streak, and sound preference are stored in
  the browser's local storage, per-device. There's no account and
  nothing is sent anywhere — it's entirely self-contained.
- The app is a single static `index.html` file plus a manifest and a
  service worker for offline caching — no build step, no server, no
  dependencies.
