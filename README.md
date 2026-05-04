# Executive Car Line — Redesign Demo

Modern premium dark/luxury redesign concept for [executivecarline.co.uk](https://www.executivecarline.co.uk/) — a one-page demo for client presentation.

## Stack

- Pure HTML / CSS / vanilla JS (no build step, no dependencies)
- Google Fonts: Cormorant Garamond + Inter
- Images served from the original Executive Car Line CDN (no copies stored locally)

## What's inside

```
executive-car-line/
├── index.html      ← entire site, single file (~37 KB)
├── README.md
└── .gitignore
```

## Features

- Cinematic hero with parallax-zoom intro and animated scroll indicator
- Sticky glassmorphism navigation
- Animated count-up stats (976 / 197 / 1611)
- 3 service cards with hover effects (Airport / Hourly / Multi-Day)
- "Why Us" feature grid (Tours / Transfers / Golf / Weddings)
- Bento-grid gallery with 5 images of Scotland
- **Working booking form** with instant quote calculator
- Testimonials section (3 original reviews)
- Contact section with real company data
- Smooth on-scroll reveal animations (`IntersectionObserver`)
- Fully responsive (desktop / tablet / mobile)

## Local preview

Just open `index.html` in any modern browser. That's it.

```
# macOS
open index.html
# Windows
start index.html
```

## Deploy to Vercel

### Option A — Vercel CLI (fastest)

```bash
npm i -g vercel
cd executive-car-line
vercel
```

Follow the prompts (login → confirm settings → deploy). You'll get a live URL like `executive-car-line-xyz.vercel.app` in ~30 seconds.

For production deploy:

```bash
vercel --prod
```

### Option B — GitHub + Vercel (auto-deploy on push)

1. Initialize a git repo and push to GitHub:

   ```bash
   cd executive-car-line
   git init
   git add .
   git commit -m "Initial redesign demo"
   git branch -M main
   git remote add origin https://github.com/<your-username>/executive-car-line.git
   git push -u origin main
   ```

2. Go to [vercel.com](https://vercel.com) → **Add New Project** → **Import Git Repository**
3. Select the repo → click **Deploy**
4. Done. Every future `git push` will redeploy automatically.

### Option C — Netlify Drop (no CLI, no git)

Drag this entire folder onto [app.netlify.com/drop](https://app.netlify.com/drop). Live URL in ~5 seconds, no account required.

## Notes for the client demo

- Site is **internet-required** because images load from executivecarline.co.uk
- For an **offline pitch** (no wifi), embed images as base64 first
- Phone numbers, emails and addresses are real — replace with test data if doing email blasts

## Customisation quick wins

- Brand colour: change `--gold` (`#c9a96e`) at the top of `<style>` in `index.html`
- Background tone: `--bg` (`#0a0a0c`)
- Hero headline: search for `Discover Scotland` in `index.html`
- Stats numbers: search for `data-target=`

---

Built as a redesign concept · not affiliated with Executive Car Line Ltd.
