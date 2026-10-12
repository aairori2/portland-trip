# Portland Trip · CANVAS 2026

A small offline-capable web app (PWA) with the day-by-day itinerary for Oct 30 – Nov 5, 2026.
Installs to the iPhone/iPad home screen and opens full screen like a native app.

## What's in it

- **Schedule** — one tab per day; on trip days it jumps to today and highlights what's happening *now* (Portland time).
- **Directions** — every stop has buttons that open Apple Maps with walking, transit or driving directions.
- **Places** — all addresses, with Map / Walk / Transit / Call / Website buttons.
- **Transit** — fares, walking times, airport and phone numbers.
- **Checklist** — tick-off list that remembers your progress on each device.
- Works **offline** after the first load.

## Files

```
index.html        the whole app (schedule data is near the top of the <script>)
manifest.json     app name, icon, colors
sw.js             offline cache
icons/            home-screen icons
```

## Host it on GitHub Pages

1. Create a new repository on GitHub, e.g. `portland-trip` (public, or private if your plan supports Pages on private repos).
2. Upload all files above, keeping the `icons/` folder.
   - On github.com: **Add file → Upload files**, drag everything in, **Commit changes**.
   - Or from a terminal:
     ```bash
     cd portland-trip
     git init && git add . && git commit -m "Portland trip app"
     git branch -M main
     git remote add origin https://github.com/<your-username>/portland-trip.git
     git push -u origin main
     ```
3. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, Branch: `main`, folder `/ (root)`, **Save**.
4. After a minute or two the site is live at `https://<your-username>.github.io/portland-trip/`.

## Install on iPhone and iPad

1. Open the link in **Safari**.
2. Tap the **Share** button → **Add to Home Screen** → **Add**.
3. Open it once while online so it caches for offline use.

## Editing the itinerary

All schedule data lives in the `DAYS`, `P` (places) and `CHECK` arrays inside `index.html`.
After editing, **bump `VERSION` in `sw.js`** (e.g. `pdx-trip-v2`) so phones pick up the change,
then commit and push. Reopen the app while online to refresh.
