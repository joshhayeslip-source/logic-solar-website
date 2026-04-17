# Logic Solar — Website

A modern, single-page marketing site for Logic Solar built with vanilla HTML, CSS, and JavaScript. Zero dependencies, zero build step.

## What's here

- **`index.html`** — The entire site. Eight pages (Home, Service, Residential, Commercial, Products, Incentives, Locations, Get a Quote) served via in-app hash routing (`#/residential`, etc.) so the whole site lives in one file.
- **`logo.png`** / **`logo-dark.png`** — Brand logos (yellow + white, yellow + black).
- **`hero-roof.jpg`** / **`groundmount-solar.jpg`** — Installation photography.
- **`vercel.json`** — Deployment config (clean URLs, headers).

## Deploying to Vercel via GitHub

### 1. Push to GitHub

```bash
git init
git add .
git commit -m "Initial Logic Solar site"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/logic-solar.git
git push -u origin main
```

### 2. Import on Vercel

1. Go to [vercel.com/new](https://vercel.com/new)
2. Import the GitHub repo
3. **Framework Preset:** "Other" (it's a static site)
4. **Build Command:** leave blank
5. **Output Directory:** leave blank (defaults to root)
6. Click **Deploy**

Vercel will serve `index.html` at your root URL. Because routing is hash-based (`#/residential`, `#/commercial`), there are no rewrite rules to configure — every URL serves the same `index.html` and the JS handles the view swap.

### 3. Custom domain

In your Vercel project: **Settings → Domains → Add**. Point your DNS at Vercel per their instructions. Done.

## Local preview

No build step. Just open `index.html` in a browser, or serve the folder:

```bash
# Python
python3 -m http.server 8000

# Node (if you have it)
npx serve

# Or just double-click index.html
```

Then visit `http://localhost:8000`.

## Editing the site

Everything lives in `index.html`:

- **Content** — the eight `<section class="view" data-view="...">` blocks inside `<main>`
- **Styles** — the single `<style>` block in `<head>`
- **Behavior** — the single `<script>` block before `</body>` (routing, animations, quote form, calculator)

There's no framework, no bundler, no `npm install`. Edit, save, refresh.

## What needs updating before launch

A few spots have placeholder content that should be replaced with real Logic Solar data:

- **Quote form submission** — currently just shows a success state. Wire it to an actual endpoint (Vercel Serverless Function, Formspree, Mailchimp, etc.)
- **Testimonials** — currently paraphrased from public Google reviews. Replace with verified first-name/last-initial attributions.
- **System prices** (Daybreak/Meridian/Eclipse) — the numbers shown are plausible starting points. Update to match actual pricing.
- **Stats in hero** — "2,840+ systems installed", "$61k avg savings", etc. are placeholders for what real Logic Solar numbers should go here.
- **Email address** — currently `contact@logic-solar.com` in footer; update if different.

## Browser support

Modern evergreen browsers (Chrome, Firefox, Safari, Edge — last 2 versions). Uses CSS Grid, backdrop-filter, and `IntersectionObserver`.

---

© 2026 Logic Solar
