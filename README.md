# Inhabitus Mockup — Vercel deploy bundle

Static site. No build step. Two ways to ship.

## Option A — Drag & drop (no install)

1. Go to https://vercel.com/new and sign in.
2. Drag this entire `Inhabitus_Deploy` folder (or the `.zip`) onto the upload area.
3. Vercel detects it as a static site, deploys, and gives you a `*.vercel.app` URL.
4. Share the URL with the client.

## Option B — CLI (one command)

```bash
cd Inhabitus_Deploy
npx vercel        # first run prompts you to log in via browser
```

Vercel asks a few questions (project name, scope) — accept defaults — and prints a preview URL. To promote it to a stable production URL: `npx vercel --prod`.

## Custom domain (optional)

In Vercel dashboard → project → Settings → Domains, add e.g. `mockup.inhabitus.pt` and follow the DNS instructions.

## Files

- `index.html` — the mockup
- `_assets/img/` — all referenced photos
- `vercel.json` — clean URLs + cache headers for assets
