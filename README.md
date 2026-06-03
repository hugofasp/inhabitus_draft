# INHabitus — Website (v3 mockup)

Static single-page mockup for **INHabitus®**. Ready to deploy to Vercel as-is — no build step, no dependencies.

- **Live entry point:** `index.html`
- **Source:** Inhabitus Mockup v3 (PROPOSTA tri-color brand system, cut-corner motif, PT-PT copy from Origem Villas Viana brochure)
- **Repo:** https://github.com/hugofasp/inhabitus_draft

---

## Structure

```
.
├── index.html          # The whole site (single-file, vanilla HTML/CSS/JS)
├── _assets/
│   └── img/            # All photography used by the page
├── vercel.json         # Static hosting config (cache headers + security headers)
├── .gitignore
└── README.md
```

---

## Run locally

No build needed — it's a static file. Pick any of:

```bash
# Python (built-in on macOS)
python3 -m http.server 8000
# → open http://localhost:8000

# Node (if you have it)
npx serve .

# Or just double-click index.html
```

---

## Deploy to Vercel

### First time (one-shot, recommended)

1. Make sure this folder is pushed to the GitHub repo (commands below).
2. Go to https://vercel.com/new → **Import** `hugofasp/inhabitus_draft`.
3. Framework Preset: **Other** (static). Leave Build Command and Output Directory **empty**.
4. Click **Deploy**. Vercel reads `vercel.json` automatically.

### Push to GitHub (from this folder)

```bash
cd Inhabitus_Deploy

# First time only — wire the remote
git remote add origin https://github.com/hugofasp/inhabitus_draft.git

# Subsequent updates
git add -A
git commit -m "Update mockup"
git push -u origin main
```

Once GitHub is wired to Vercel, every push to `main` triggers a redeploy.

### Or deploy from CLI

```bash
npm i -g vercel    # one-time
vercel             # preview deploy
vercel --prod      # production deploy
```

---

## Editing in Claude Code

Open this folder in Claude Code and ask things like:

- *"Tweak the hero copy and redeploy."*
- *"Swap `_assets/img/hero_villa.jpg` for the new one in `~/Downloads`."*
- *"Add a new section before the footer using the existing brand styles."*

Claude Code will edit `index.html`, you commit and push, Vercel rebuilds automatically.

---

## Notes

- **No framework.** Everything is in one HTML file. CSS variables in `:root` carry the brand palette and the cut-corner polygon clip-paths.
- **Images are heavy** (~4 MB total). For better Lighthouse scores, run them through `sharp`/`squoosh` to generate WebP variants before launch.
- **Forms are visual only.** The contact form in the footer has `onsubmit="event.preventDefault();"`. Wire it to a real endpoint (Formspree, Resend, your own API) when ready.
- **Languages:** PT-PT only for now. A `PT / EN` toggle is in the nav but not wired up.
