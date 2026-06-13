# YuanU Medical Concierge — Website

Static bilingual (EN / 中文) marketing site for YuanU Medical Concierge.
Pure HTML + inline CSS. No build step. Ready for GitHub + Vercel.

---

## Pages

| File                     | Section                          |
| ------------------------ | -------------------------------- |
| `index.html`             | Home                             |
| `about.html`             | About YuanU                      |
| `why-beijing.html`       | Why Beijing / Why Friendship     |
| `screening.html`         | Health screening packages        |
| `endoscopy.html`         | Endoscopy / treatment            |
| `patient-support.html`   | Patient journey & support        |
| `other-services.html`    | Non-medical travel services      |
| `faq.html`               | FAQ                              |
| `contact.html`           | Contact (email + future form)    |
| `404.html`               | Not-found page                   |

Other files:

| File              | Notes                                                       |
| ----------------- | ----------------------------------------------------------- |
| `favicon.svg`     | Brand mark, dark navy + gold                                |
| `robots.txt`      | Currently disallow-all (staging). Replace before launch.    |
| `.gitignore`      | Standard JS / editor / Vercel ignores                       |
| `images/`         | Placeholder for product images (empty for now)              |
| `css/`            | Reserved for extracted stylesheets (empty for now)          |
| `js/`             | Reserved for extracted scripts (empty for now)              |

---

## Local preview

No build needed. Either:

```bash
python3 -m http.server 8080
# open http://localhost:8080
```

or just double-click `index.html`.

---

## Deploy: GitHub + Vercel

### 1. Create the repo

```bash
cd yuanumedical_web
git init
git add .
git commit -m "Initial commit — YuanU Medical site v1"
git branch -M main
git remote add origin https://github.com/<your-org>/yuanumedical-web.git
git push -u origin main
```

### 2. Import to Vercel

1. Go to [vercel.com/new](https://vercel.com/new) → import the GitHub repo.
2. Framework Preset: **Other** (static site, no build command needed).
3. Build & Output settings: leave defaults — Vercel will serve files as-is from the repo root.
4. Click **Deploy**. You'll get a free `*.vercel.app` preview URL immediately.

### 3. Bind the production domain (after purchase)

Once `yuanumedical.com` is purchased:

1. Vercel project → **Settings → Domains** → add `yuanumedical.com` and `www.yuanumedical.com`.
2. Update the DNS records at the registrar as Vercel instructs (A / CNAME).
3. SSL is auto-issued (Let's Encrypt).
4. **Update `robots.txt`** — replace the disallow-all block with the production version commented at the top of the file.

---

## Bilingual switch

Implemented purely in CSS via `body[data-lang="en" | "zh"]`:

- `<span class="lang-en">…</span>` shown when `data-lang="en"`
- `<span class="lang-zh">…</span>` shown when `data-lang="zh"`

The toggle button at the top-right calls a small inline `<script>` that flips `data-lang` and `<html lang>` together. No external JS framework.

---

## Contact form (interim)

`contact.html` currently uses `mailto:zhangjianping@yuanu.com` as the form action — clicking **Send via email** opens the visitor's default mail client with the form contents pre-filled.

When ready, swap to a backend form service (recommended order):

- **Formspree** — free tier, drop-in `action="https://formspree.io/f/<id>"` works without changing field names.
- **Tally** / **Google Forms** — embed an iframe, or replace the section entirely.
- **Vercel Forms** — only available on Pro plans, embed via React/Next; not needed for a static site.

---

## Open items (waiting on the client side)

- [ ] Real images for hero, hospital exterior / interior, doctors, journey illustrations → drop into `images/` and reference as `<img src="images/<filename>" alt="…">`.
- [ ] WeChat QR code, phone number, additional contact channels (will be added to `contact.html` once provided).
- [ ] Production domain `yuanumedical.com` purchase + DNS pointing to Vercel.
- [ ] Replace `robots.txt` with the production version after launch.
- [ ] (Optional) Extract inline CSS into `css/site.css` for easier maintenance.
- [ ] (Optional) Add `sitemap.xml` and Google Search Console verification after domain is bound.

---

## Maintainer note

All internal links use relative paths (`about.html`, `contact.html`, …) — safe under GitHub Pages, Vercel, or any static host. No Coze preview URLs are referenced anywhere.
