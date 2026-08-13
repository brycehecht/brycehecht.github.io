# Deploying to GitHub Pages

## 1. Create the repo

Name it **exactly** `yourusername.github.io` — that gives you `https://yourusername.github.io`
with no subpath. (Any other name works too, but the URL becomes `username.github.io/reponame`.)

Make it **public**. Private repos need a paid plan for Pages.

## 2. Add the files

Upload to the repo root:

```
index.html     ← the site
photo.jpg      ← your headshot, square, ~600×600px (optional; hides itself if missing)
cv.pdf         ← your CV (optional)
```

Drag-and-drop works: **Add file → Upload files** on the repo page.

## 3. Turn on Pages

**Settings → Pages → Source: Deploy from a branch → `main` / `(root)` → Save**

Live in 1–2 minutes. Every push republishes automatically.

## 4. Custom domain (optional)

If you own e.g. `brycehecht.com`:

1. At your DNS provider, add four `A` records for the apex domain pointing to
   `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
2. Add a `CNAME` record for `www` → `yourusername.github.io`
3. In **Settings → Pages → Custom domain**, enter the domain and check **Enforce HTTPS**

---

# Editing the site

Everything is in `index.html`. Search for `TODO` — every placeholder is marked.

**Colors** live at the top of the `<style>` block in `:root`. Change `--accent` to
recolor every link and highlight at once. The `@media (prefers-color-scheme: dark)`
block below it sets the dark-mode palette; both need editing if you change the theme.

**Adding a publication** — copy one `<article class="pub">` block and edit. Wrap your own
name in `<span class="me">` so it bolds. The `<span class="tag">` is optional (use it for
Preprint, Best Paper, Under Review, etc.).

**Adding a year** — copy `<p class="year-head">2026</p>` plus its `<div class="pubs">` wrapper.

**Removing a section** — delete the whole `<section>` block and its `<li>` in the nav.

**Fonts** load from Google Fonts. To drop the external dependency, delete the two
`<link>` tags in `<head>`; the CSS falls back to system sans-serif and still looks fine.

## Editing directly on GitHub

You don't need git installed. Open `index.html` in the repo, click the pencil icon,
edit, and **Commit changes**. The site rebuilds automatically.
