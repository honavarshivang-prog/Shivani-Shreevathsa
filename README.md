# Shivani & Shreevathsa — Wedding Invitation Website

React + Vite. No UI libraries. Static output, ready for GitHub Pages.

## Edit content
- **Everything** (names, date, venue, events, times, tentative flags, RSVP date, Maps link, music, photo files, alt text, captions) lives in `src/data/weddingData.js`.
- To replace a photo: overwrite the file in `public/images/` (keep the name) **or** change its `src` in `weddingData.js`. Set the correct `w`/`h` pixel size so layout doesn't jump.
- Music: put an MP3 in `public/audio/music.mp3`, then set `music: \`${BASE}audio/music.mp3\`` in `weddingData.js`.
- RSVP: `src/rsvp.js` is the only place that sends data. Until you set `rsvpEndpoint`, submissions are simulated and **not saved**.

## Run locally
```
npm install
npm run dev
```

## Deploy to GitHub Pages
1. Create a GitHub repo (e.g. `wedding`) and push this project to the `main` branch:
   ```
   git init && git add . && git commit -m "Wedding site"
   git branch -M main
   git remote add origin https://github.com/<you>/wedding.git
   git push -u origin main
   ```
2. Publish:
   ```
   npm install
   npm run deploy
   ```
   This builds to `dist/` and pushes it to the `gh-pages` branch.
3. In GitHub: **Settings → Pages → Source: Deploy from a branch → `gh-pages` / `/ (root)`**.
4. Your site is at `https://<you>.github.io/wedding/` (in a minute or two).

Asset paths use `base: "./"` in `vite.config.js`, so any repo name works. After changing content, run `npm run deploy` again.
