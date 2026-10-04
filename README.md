# Serena Zhang · Portfolio

Personal portfolio site built with [Astro](https://astro.build). Static pages, deployed on Vercel.

## Pages

| URL | File |
| --- | --- |
| `/` | `src/pages/index.astro` (home: work, competitions, about, resume, contact) |
| `/work/ip-ai-stories` | `src/pages/work/ip-ai-stories.astro` |
| `/work/tilo` | `src/pages/work/tilo.astro` |
| `/work/family-account` | `src/pages/work/family-account.astro` |

- `src/layouts/Base.astro` holds the shared `<head>`: fonts, page title, description, social preview image, favicon.
- Each page keeps its own styles in a `<style is:global>` block at the top of the file.
- Images and videos live in `public/media/<page>/` and are referenced as `/media/<page>/<file>`.

## Run it on your computer

Needs Node.js 18.20+ (20 or 22 recommended).

```bash
npm install
npm run dev      # http://localhost:4321
npm run build    # outputs the static site to dist/
```

## Publish: GitHub + Vercel

1. Create an empty repository on GitHub (for example `serena-portfolio`).
2. In this folder:
   ```bash
   git init
   git add .
   git commit -m "Portfolio site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/serena-portfolio.git
   git push -u origin main
   ```
3. On vercel.com: **Add New → Project → Import** the repository. Vercel detects Astro automatically (build `npm run build`, output `dist`). Click **Deploy**.
4. Custom domain: Vercel project → **Settings → Domains → Add** your domain, then add the DNS records Vercel shows at your domain registrar.
5. Update `site` in `astro.config.mjs` to your real domain and push again.

Every later `git push` to `main` redeploys automatically.

## Adding a new case study

1. Copy an existing file in `src/pages/work/` and rename it (the file name becomes the URL).
2. Put its images in `public/media/<new-name>/`.
3. Add a card for it in the "Selected work" section of `src/pages/index.astro`, and update the previous/next links at the bottom of the neighbouring case studies.
