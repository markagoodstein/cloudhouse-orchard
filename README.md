# Orchard Management

A phone-and-desktop app for running a home orchard: weekly tasks, per-tree care and feeding, harvest dates, chill hours and local station weather.

The app holds no orchard data. Each orchard is a folder in the owner's Dropbox, in an open, documented format (JSON + GeoJSON + Markdown; see the `README.md` and `schema/` inside an orchard folder). Every device keeps a full copy of that folder, works offline, and syncs changes both ways when it has a connection.

## Use it

1. Put an orchard folder (one containing `orchard.json`) anywhere in your Dropbox.
2. Open the app, tap **Connect Dropbox**, approve, and pick the folder.
3. On iPhone: Safari → Share → **Add to Home Screen**. In the home-screen app, Dropbox shows a code after you approve; copy it and paste it into the app.

## How sync works

- Records are small files, one per tree, program or task. Edits are saved on the device first, then uploaded.
- If two people change the same record, the later edit wins; the other version is kept in `history/` so nothing is lost.
- Every change is appended to `history/<person>-<device>/<YYYY-MM>.jsonl`.
- Dropbox's own version history is a second backstop.

## Privacy

- The app's code is public; orchard data stays in your Dropbox and on your devices.
- The Wunderground API key is entered on each device and never written to Dropbox or this repository.
- Dropbox access can be revoked at dropbox.com → Settings → Connected apps.
