# tiffany-boccieri.github.io

Campaign site for Tiffany Boccieri for Laguna Hills City Council, District 4.
Plain static HTML/CSS — no build step, no framework.

Served by GitHub Pages directly from the `main` branch, at the custom domain
in [`CNAME`](CNAME).

## Local preview

No dependencies needed — just Python's built-in server:

```bash
python -m http.server 8000
```

Then open http://localhost:8000 in a browser. Stop the server with Ctrl+C.

## Structure

- `index.html` — the English site (single page)
- `es/index.html`, `fa/index.html` — Spanish and Farsi (right-to-left) versions
- `style.css` — all styles, shared by every language
- `sitemap.xml` — lists all three pages with `hreflang` alternates
- `assets/` — images
- `CNAME` — custom domain for GitHub Pages

## Languages

Each language is its own page and URL (`/`, `/es/`, `/fa/`) so each can be
indexed, shared, and linked on its own. When site copy changes, update all three
pages and keep section `id`s (`about`, `issues`, `connect`) identical, since the
language switcher preserves the visitor's place on the page.

Spanish and Farsi copy comes from the campaign's translation sheet (one entry per
string ID). When English copy changes, update the matching sheet entry and have a
native speaker re-check the Spanish and Farsi before publishing. On the Farsi
page, wrap any English words (place names, the committee name, etc.) in
`<bdi lang="en">` so they display correctly in right-to-left text.

## Workflow

- Commit directly to `main` for small edits — GitHub Pages redeploys
  automatically within a minute or two of a push.
- For anything you want to review before it's live, work on a branch and
  open a pull request instead.
