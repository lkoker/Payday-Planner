# Payday Planner (PWA)

Installable version of Payday Planner. It runs full-screen with its own icon, works offline, and keeps your data on the phone.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole app |
| `manifest.webmanifest` | App name, icon, and colors for "Install app" |
| `sw.js` | Service worker: offline support and caching |
| `icon-192.png`, `icon-512.png`, `icon-maskable-512.png` | Home-screen icons |

## Put it online (GitHub Pages, free)

Easiest from your PC:

1. Create a new **public** repo on GitHub, for example `payday-planner`.
2. Click **Add file → Upload files**, drag in all six files above, and commit.
3. Go to **Settings → Pages**. Set **Source** to *Deploy from a branch*, choose **main** and **/ (root)**, then save.
4. After about a minute, your app is at `https://<your-username>.github.io/payday-planner/`.

The repo being public is fine. It holds only the app code. Your bills and pay never leave your phone.

Prefer the command line?

```bash
cd payday-planner
git init && git add . && git commit -m "Payday Planner PWA"
gh repo create payday-planner --public --source=. --push
gh api -X POST repos/{owner}/payday-planner/pages -f "source[branch]=main" -f "source[path]=/"
```

## Install on your Pixel

1. Open your `github.io` link in Chrome.
2. Tap **⋮ → Install app** (or **Add to Home screen → Install**).
3. Open it from the new icon. It runs without the Chrome address bar.

## Move your data over from the Claude version

1. In the Claude version, open **Settings (gear) → Copy backup**.
2. In the installed app, open **Settings → Restore backup**, paste, and tap **Restore pasted backup**.

## Keep a backup

Your data lives in the app's storage on your phone. Uninstalling the app or clearing Chrome's site data erases it. Every so often, go to **Settings → Save backup file**, which saves a `.json` file to Downloads. You can restore it with **Restore backup → Choose file**.

## Updating the app later

1. Edit `index.html` (or ask Claude for changes) and upload the new file to the repo.
2. In `sw.js`, bump `VERSION` (for example `payday-v1` → `payday-v2`) so phones load the new version.
3. Close and reopen the app once or twice to pick up the change.
