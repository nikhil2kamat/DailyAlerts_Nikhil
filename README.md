# Alerts Timeline (GitHub Pages)

A lightweight, single‑page app to list your alerts in chronological order. It auto‑loads from `alerts.json` in the same repo by default (no backend needed).

## Quick start (GitHub website UI)

1. Create a **new public repo** on GitHub, e.g. `alerts-timeline`.
2. Upload these files to the repo root:
   - `index.html`
   - `alerts.json`
   - `.nojekyll` (empty file)
3. Commit the changes.
4. Go to **Settings → Pages**. Under **Build and deployment**, choose:
   - **Source**: *Deploy from a branch*
   - **Branch**: `main` (or `master`), **Folder**: `/ (root)`
5. Save. In ~1 minute, your site will be live at:
   - `https://<your-username>.github.io/<repo>/`

Open the site; it will automatically load `alerts.json` and show your items. The page refreshes automatically every 10 minutes (configurable).

> Tip: You can override the feed (e.g., a different JSON URL) by appending `?feed=https://.../your.json` to the page URL.

## Editing the data

- Open `alerts.json` and append new items to the JSON array.
- Each item should include:
```json
{
  "id": "unique-id-123",
  "category": "Company News (8 AM)",
  "companyTopic": "PI Industries",
  "title": "Headline",
  "summary": "1–3 lines",
  "link": "https://example.com",
  "sentAt": "2025-08-24T12:00:00+05:30"
}
```
- `sentAt` can be any ISO8601 datetime. If you include the IST offset `+05:30`, the page will display the correct local time.

## Optional: Git from your laptop

```bash
git clone https://github.com/<your-username>/alerts-timeline.git
cd alerts-timeline
# copy the files from this zip into the folder (index.html, alerts.json, .nojekyll)

git add .
git commit -m "Initial commit: alerts timeline"
git push origin main
```

## Why `.nojekyll`?

GitHub Pages uses Jekyll by default and may ignore files/folders starting with underscores. This app doesn’t need Jekyll, so we add `.nojekyll` to bypass it.

## License

MIT – do whatever you like, no warranty.
