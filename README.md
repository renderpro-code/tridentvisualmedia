# Trident Visual Media — Author Website

Hugo static site for [tridentvisualmedia.com](https://tridentvisualmedia.com)

**Stack:** Hugo + Congo theme · Cloudflare Pages · Decap CMS · Kit (email)

---

## Quick Start (local development)

```bash
# Clone repo with Congo submodule
git clone --recurse-submodules https://github.com/YOURUSERNAME/tridentvisualmedia.git
cd tridentvisualmedia

# Start local dev server (live reload)
hugo server -D

# Visit: http://localhost:1313
```

---

## Adding a New Book

1. Open `tridentvisualmedia.com/admin` — log in with GitHub
2. Click **Books → New Book**
3. Fill in: title, series, blurb, cover image, Amazon URL, date
4. Click **Publish** — Cloudflare deploys automatically in ~30 seconds

Or locally:
```bash
# Create the .md file in the correct series folder
hugo new series/miller-crime-thriller/book-title.md
```

---

## Adding a New Blog Post

Via CMS: **Blog Posts → New Blog Post**

Or locally:
```bash
hugo new blog/your-post-slug.md
```

---

## File Structure

```
tridentvisualmedia/
├── config/_default/
│   ├── hugo.toml          ← Main Hugo config
│   ├── params.toml        ← Congo theme settings
│   └── menus.toml         ← Navigation links
├── content/
│   ├── _index.md          ← Homepage
│   ├── about.md           ← About page
│   ├── newsletter/        ← Email signup page
│   ├── blog/              ← Blog posts (SEO engine)
│   └── series/
│       ├── miller-crime-thriller/
│       │   ├── _index.md              ← Series landing page
│       │   └── the-counting-man.md    ← Book page
│       └── echoes-of-the-void/
│           └── _index.md              ← Series landing (pre-launch)
├── static/
│   ├── admin/
│   │   ├── index.html     ← Decap CMS entry point
│   │   └── config.yml     ← CMS field definitions
│   └── images/            ← Book covers, author photo, hero image
├── assets/css/
│   └── custom.css         ← Brand overrides (buy buttons, etc.)
├── layouts/shortcodes/
│   └── buy-links.html     ← {{< buy-links amazon="..." >}} shortcode
├── themes/congo/           ← Congo theme (git submodule)
├── wrangler.toml           ← Cloudflare Pages build config
└── .gitignore
```

---

## Deploying

Push to `main` → Cloudflare Pages auto-builds and deploys.

```bash
git add .
git commit -m "your message"
git push
```

Live in ~30 seconds.

---

## CMS Access

`https://tridentvisualmedia.com/admin`

Authenticate with GitHub. Edits commit to `main` and trigger a deploy automatically.

---

## TODO on first deploy

- [ ] Replace `YOURUSERNAME` in `static/admin/config.yml`
- [ ] Add real book blurb to `the-counting-man.md`
- [ ] Replace `YOUR-ASIN-HERE` with real Amazon ASIN
- [ ] Add hero image: `static/images/hero-bg.jpg`
- [ ] Add book cover: `static/images/books/the-counting-man-cover.jpg`
- [ ] Add author/logo: `static/images/trident-logo.png`
- [ ] Paste Kit embed code into `content/newsletter/_index.md`
- [ ] Set up Cloudflare Pages GitHub OAuth for CMS login
- [ ] Submit sitemap to Google Search Console: `tridentvisualmedia.com/sitemap.xml`
