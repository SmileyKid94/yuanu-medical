# YuanU Medical · Uniform-v5 Pass Notes

**Date:** 2026-07-14
**Scope:** Fix the three site defects raised by Sir & 谭笑 on 2026-07-14.
**Deploy:** Same as v2 (static files, no build step). Unzip → commit → push. Vercel auto-deploys.

---

## Why this pass was needed

Three defects were found on the live site and inside the `SmileyKid94/yuanu-medical` repo:

1. **`index.html` had a header/footer with no styling.**
   The v2 `<header class="site-header">` / `<footer class="site-footer">` HTML was in the file, but `assets/css/site.css` **did not contain any styles for `.site-header` / `.site-footer`** (the CSS file only ships `.content` typography and testimonials/insurance styles). As a result, the live home page was showing an unstyled row of link text at the top instead of a proper nav bar.
2. **Four pages had *no* header/footer at all.**
   `insurance-direct-billing.html`, `privacy-policy.html`, `terms-of-service.html` and `testimonials.html` only contained the placeholder comments
   `<!-- @include: /partials/header.html -->` and `<!-- @include: /partials/footer.html -->`.
   The current deploy is pure static hosting (no SSI / no build step), so these comments are ignored by the browser — visitors saw article text hitting the browser edge with no header, no footer, no way to navigate.
3. **Two mismatched templates coexisted across 13 pages.**
   Eight content pages (`about.html`, `contact.html`, `endoscopy.html`, `screening.html`, `faq.html`, `why-beijing.html`, `patient-support.html`, `other-services.html`) had already been upgraded to the **v5 design system** (deep teal + cold gold, Cormorant Garamond + Inter, `topbar` + `lang-toggle` bilingual toggle). Five legacy pages (index + the four include-only pages above) were still stuck on the incomplete v2 template. Switching between pages caused a visible break in look-and-feel and navigation.

谭笑's ask was explicit: *"具体页面里的格式代码需要统一 · 给我一个纯净版压缩包，解压完直接 commit 就能覆盖更新网页."* This pass does exactly that.

---

## What changed

### 5 pages upgraded from v2 to v5 topbar/footer

| Page | Header before | Footer before | Header after | Footer after |
|---|---|---|---|---|
| `index.html` | `<header class="site-header">` (no CSS) | `<footer class="site-footer">` (no CSS) | `<header class="topbar">` (v5) | `<footer class="site-foot">` (v5) |
| `insurance-direct-billing.html` | `<!-- @include ... -->` | `<!-- @include ... -->` | v5 topbar (inline) | v5 footer (inline) |
| `privacy-policy.html` | `<!-- @include ... -->` | `<!-- @include ... -->` | v5 topbar (inline) | v5 footer (inline) |
| `terms-of-service.html` | `<!-- @include ... -->` | `<!-- @include ... -->` | v5 topbar (inline) | v5 footer (inline) |
| `testimonials.html` | `<!-- @include ... -->` | `<!-- @include ... -->` | v5 topbar (inline) | v5 footer (inline) |

Every page now carries:
- `<html lang="en" data-lang="en">` and `<body data-lang="en">` (needed for the EN/中文 toggle)
- Google Fonts preconnect + font stylesheet (`Cormorant Garamond`, `Inter`, `Noto Serif SC`, `Noto Sans SC`, `JetBrains Mono`)
- A **scoped v5 topbar+footer shim** inside a new `<style>` block: only tokens + `.topbar` + `.site-foot` selectors (page-scoped, prefixed with `.topbar` / `.site-foot`, so it does **not** override the page body typography or existing v2 section styles)
- The v5 topbar HTML (with `Home` active on `index.html`, no nav item marked active on the 4 legal/info pages)
- The v5 footer HTML (four-column dark teal footer with license line)
- The v5 `lang-toggle` `<script>` at the bottom of `<body>`

**Nothing in the page body was touched.** All the hero copy, services grid, hospital cards, insurance content, testimonials list and legal text are byte-for-byte the same as before, except header and footer.

### 8 already-v5 pages: **NOT touched**

`about.html`, `contact.html`, `endoscopy.html`, `screening.html`, `faq.html`, `why-beijing.html`, `patient-support.html`, `other-services.html` — md5 identical to previous main branch. No risk of regression on those pages.

### `partials/header.html` and `partials/footer.html`: updated to v5

The reference partial files were also rewritten in the same v5 style, so if a build tool is ever introduced later (SSI / Vercel Edge / 11ty / Astro), it will emit the correct v5 markup out of the box. A comment at the top explains that the live pages currently ship the topbar/footer inline, so these partials are for future use only.

### `assets/css/site.css`: kept

Still referenced by `index.html`, `insurance-direct-billing.html`, `privacy-policy.html`, `terms-of-service.html`, `testimonials.html`. It provides the `.content` typography (h1/h2/h3, tables, testimonial cards, insurance-note callout) for those pages. Removing it would break the article body layout on the four legal/info pages, so it's left in place.

### `zh/` directory: unchanged

The Chinese privacy/terms summary pages under `zh/` were not touched in this pass. If Sir wants those two Chinese-language pages upgraded next, we can run the same script over them.

---

## What this pass explicitly does *not* do

- Does **not** change any body copy, legal text, medical language or SEO metadata.
- Does **not** remove `assets/css/site.css` (the four legal/info pages still depend on it for article typography).
- Does **not** upgrade the two `zh/*.html` files.
- Does **not** touch the 8 already-v5 pages.

---

## Deploy steps (for 谭笑)

```bash
# 1. Unzip
unzip yuanu-medical-uniform-v5-20260714.zip

# 2. Copy all files over the local checkout of SmileyKid94/yuanu-medical
#    (the zip is already flat at the repo root, so `cp -r * /path/to/repo/` works)

# 3. Commit
cd /path/to/yuanu-medical
git add -A
git commit -m "Uniform v5: fix broken header/footer on index + 4 legal pages, sync to v5 topbar/footer"
git push origin main

# 4. Vercel auto-deploys within ~30s. Verify:
#    - https://beijinghealthcarenavigation.com/           → v5 topbar visible, home page active
#    - https://beijinghealthcarenavigation.com/insurance-direct-billing.html → topbar + footer visible
#    - https://beijinghealthcarenavigation.com/privacy-policy.html         → topbar + footer visible
#    - https://beijinghealthcarenavigation.com/terms-of-service.html       → topbar + footer visible
#    - https://beijinghealthcarenavigation.com/testimonials.html           → topbar + footer visible
#    - Click 中文 in the top-right toggle → all pages should switch language and remember the choice
```

If any of the 8 v5 content pages break after commit, that's unexpected — this pass did not touch them.

---

## Contact

- Sir · zhangjianping@yuanu.com  ·  contact@yuanu.com (CC)
- 高亢 (medical review) · YMYL sign-off pending
- 谭笑 (tech / deploy) · uiuzyforever0618@gmail.com

License: L-BJ-CJ00262 · Beijing YuanU International Travel Co., Ltd. · 2026
