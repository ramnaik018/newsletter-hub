# Newsletter Hub

A static website showcasing my AI/ML/GenAI and Finance newsletter editions. Built for GitHub Pages — no frameworks, no build step.

**Live site:** `https://<your-username>.github.io/newsletter-hub/`

---

## Quick Start

```bash
# Clone and open locally
cd newsletter-hub
open index.html
```

That's it. No server needed.

---

## How to Update When You Publish a New Edition

1. Open `data.json`
2. Find the edition you just published (search by title)
3. Change these fields:

```json
{
  "number": 5,
  "title": "From Linear Models to Neural Networks",
  "hook": "A linear model is just one neuron...",
  "status": "published",          ← change from "planned" to "published"
  "linkedin_url": "https://www.linkedin.com/pulse/...",  ← paste your article URL
  "published_date": "2026-05-10"  ← add the publish date (YYYY-MM-DD)
}
```

4. Commit and push:

```bash
git add data.json
git commit -m "Published Edition 5: Neural Networks"
git push
```

Site updates in ~30 seconds.

---

## Status Values

| Status | What it means | How it displays |
|--------|--------------|-----------------|
| `"published"` | Live on LinkedIn | Green checkmark, "Read →" link |
| `"writing"` | Currently working on it | Yellow pen icon, "This Week" badge |
| `"planned"` | Future topic | Grey dot, "Coming Soon" badge |

---

## Mark an Edition as "Currently Writing"

Change `status` from `"planned"` to `"writing"`:

```json
"status": "writing"
```

This highlights it in the "Coming Up Next" section with a yellow badge.

---

## Deploy to GitHub Pages

1. Create a repo called `newsletter-hub` on GitHub
2. Push this folder:

```bash
cd newsletter-hub
git init
git add .
git commit -m "Initial commit: newsletter hub"
git branch -M main
git remote add origin https://github.com/<your-username>/newsletter-hub.git
git push -u origin main
```

3. Go to **Settings → Pages → Source → Deploy from branch → main → / (root)**
4. Wait 1-2 minutes → your site is live at `https://<your-username>.github.io/newsletter-hub/`

---

## File Structure

```
newsletter-hub/
├── index.html    ← The entire website (HTML + CSS + JS)
├── data.json     ← All edition data (this is what you edit)
└── README.md     ← This file
```

---

## Customization

### Change profile info
Edit the `"profile"` section in `data.json`:

```json
"profile": {
  "name": "Ramnaik Guguloth",
  "tagline": "Making complex topics click — one edition at a time",
  "linkedin_url": "https://linkedin.com/in/your-profile",
  "newsletter_subscribe_url": "https://linkedin.com/newsletters/..."
}
```

### Add a new newsletter
Add a new object to the `"newsletters"` array in `data.json` following the same structure.

### Change colors
Edit the CSS variables at the top of `index.html` inside the `:root` block.

---

## Tips

- Keep `linkedin_url` as `null` (not `""`) for unpublished editions
- The "Latest Edition" card automatically picks the most recently published one
- "Coming Up Next" shows the next 3 editions that aren't published yet
- Use URL hash (`#ml` or `#finance`) to link directly to a specific newsletter tab
