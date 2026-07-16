# Food Delivery Weekly Digest — Site

Mobile-friendly static archive. One URL for all historical weeks.

## Local preview

```bash
cd "/Users/didi/Desktop/Work/外卖/AI/Newsletter/site"
python3 -m http.server 8080
```

Open `http://localhost:8080` on your phone (same Wi‑Fi) via your computer’s LAN IP, or use a tunnel later after deploy.

`file://` will not load `data/weeks.json` (browser security). Always use a local server or hosted URL.

## Add a new week (e.g. Week 29)

1. Create `weeks/2026-w29.html` (copy `weeks/2026-w28.html`, replace content).
2. Prepend an entry in `data/weeks.json`:

```json
{
  "id": "2026-w29",
  "week": 29,
  "year": 2026,
  "label": "Week 29",
  "start": "2026-07-13",
  "end": "2026-07-19",
  "rangeDisplay": "2026/07/13–2026/07/19",
  "href": "weeks/2026-w29.html",
  "summary": "One-line highlight of the week."
}
```

3. Redeploy the `site/` folder. The archive homepage updates automatically.

ISO week tip: Week 28 = 2026/07/06–2026/07/12; Week 29 = 2026/07/13–2026/07/19.

## Deploy (pick one — keeps one stable link)

### Cloudflare Pages (recommended)

1. Create a Git repo containing this `site/` folder (or the parent Newsletter folder).
2. Cloudflare Dashboard → Workers & Pages → Create → Connect repo.
3. Build: none. Output directory: `site` (or `/` if the repo root is `site/`).
4. Share the `*.pages.dev` URL (or custom domain).

### GitHub Pages

1. Push `site/` to a GitHub repo.
2. Settings → Pages → Deploy from branch → `/` or `/docs` / `site`.
3. Share `https://<user>.github.io/<repo>/`.

### Netlify Drop

Drag the entire `site/` folder onto [https://app.netlify.com/drop](https://app.netlify.com/drop) for an instant URL (good for a quick share).

## Skill integration

When generating a digest with the `food-delivery-weekly-digest` skill, ask to **publish to the site** so Week N HTML + `weeks.json` are updated in the same pass.
