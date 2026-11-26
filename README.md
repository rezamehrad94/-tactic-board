# Tactic Board ⚽

A football tactics board that runs in the browser and works **online and offline** (installable PWA).

- Clubs and national teams, each with three modes: **Starting XI**, **Possession & Attack**, **Defending**
- 18 formations, drag players anywhere, run arrows, captain, kit-colour pitch
- **Match** view: two teams on one pitch (home on top), vertical or horizontal
- Copy / paste whole teams, up to 30 players per team
- Export a lineup image, share a lineup as text

Everything is a single `index.html` (no build step, no dependencies).

## Put it on GitHub Pages

1. Create a new repository on GitHub (for example `tactic-board`).
2. Upload **all files in this folder** (keep the `icons/` folder): `index.html`, `manifest.webmanifest`, `sw.js`, `.nojekyll`, `icons/`.
   - Or with git:
     ```bash
     git init
     git add .
     git commit -m "Tactic Board"
     git branch -M main
     git remote add origin https://github.com/<you>/tactic-board.git
     git push -u origin main
     ```
3. In the repository: **Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)` → Save**.
4. After a minute the app is live at `https://<you>.github.io/tactic-board/`.

## Install it and use it offline

- **iPhone (Safari):** open the link → Share → *Add to Home Screen*.
- **Android (Chrome):** open the link → menu → *Install app*.
- Open it once while online. After that it works with no connection.

## Updating

After you change `index.html`, edit the first lines of `sw.js` and bump the version (`v1` → `v2`), then commit.
Online users get the new version on their next visit (the old one is shown once, then it refreshes in the background).

## Your data

Teams, lineups and settings are stored in the browser (`localStorage`) on each device. They are not synced between devices and are lost if the browser data is cleared.
Use **Copy team** → paste it somewhere (a note, a chat) to back a team up, and **Paste team** to restore it.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app |
| `manifest.webmanifest` | Install metadata (name, icons, colours) |
| `sw.js` | Offline cache |
| `icons/` | App icons (SVG + PNG, maskable included) |
