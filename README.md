# Erin's Workout App

A guided weekly workout program with embedded MadFit YouTube videos, run tracking, and progress logging. Installable as a PWA (home screen app) on iPhone.

## Deploy to GitHub Pages

1. **Copy these files** into your repo (e.g. `kearnj-code.github.io` or a new repo `erin-workout`):
   ```
   index.html
   manifest.json
   sw.js
   icons/
     icon-192.png
     icon-512.png
     apple-touch-icon.png
     apple-touch-icon-152.png
     apple-touch-icon-167.png
     favicon-32.png
   ```

2. **If using a subfolder repo** (e.g. `github.com/kearnj-code/erin-workout`):
   - Go to repo **Settings → Pages**
   - Set source: `main` branch, `/ (root)`
   - Your URL will be: `https://kearnj-code.github.io/erin-workout/`
   - **Update `manifest.json`** — change `"start_url"` to `"/erin-workout/"`

3. **If using root of `kearnj-code.github.io`**:
   - Drop files directly in the repo root
   - Change `"start_url"` in `manifest.json` to `"/"`

## iPhone "Add to Home Screen"

Once live on GitHub Pages:
1. Open the URL in **Safari** on Erin's iPhone
2. Tap the **Share button** (box with arrow)
3. Tap **"Add to Home Screen"**
4. Name it "Erin's Fit" → tap **Add**

The app will appear on her home screen like a native app — fullscreen, no browser chrome, and localStorage will be stable because it's tied to a real HTTPS origin.

## Storage

All workout progress is saved to `localStorage` under the key `erinFitState`. As long as Erin doesn't clear Safari data, it will persist indefinitely once installed as a PWA.

## Updating the App

Edit `index.html`, push to GitHub. The service worker will update automatically on next visit. If you need to force a cache refresh, bump the version in `sw.js`: `const CACHE_NAME = 'erin-workout-v2';`
