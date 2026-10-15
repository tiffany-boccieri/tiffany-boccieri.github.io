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
- `positions/` — issue position pages (`index.html` plus one folder per topic); `es/positions/` and `fa/positions/` mirror them
- `style.css` — all styles, shared by every language
- `sitemap.xml` — lists all three pages with `hreflang` alternates
- `assets/` — images
- `CNAME` — custom domain for GitHub Pages

## Languages

Each language is its own page and URL (`/`, `/es/`, `/fa/`) so each can be
indexed, shared, and linked on its own. When site copy changes, update all three
pages and keep section `id`s (`about`, `issues`, `connect`) identical, since the
language switcher preserves the visitor's place on the page.

The Positions pages are translated the same way, at `/es/positions/...` and `/fa/positions/...` with identical slugs; a new or edited position needs all three versions and `sitemap.xml` entries with `hreflang` alternates.

Spanish and Farsi copy comes from the campaign's translation sheet (one entry per
string ID). When English copy changes, update the matching sheet entry and have a
native speaker re-check the Spanish and Farsi before publishing. On the Farsi
page, wrap any English words (place names, the committee name, etc.) in
`<bdi lang="en">` so they display correctly in right-to-left text.

## Positions

Each position is its own page at `/positions/<slug>/` so it can be linked from
social posts and found by search. Slugs are permanent once shared. For a new
position: copy an existing folder, update the title, description, canonical, Open
Graph, JSON-LD (headline, dates), breadcrumb, answer box, sources, and the
"More positions" cards, then add the page to `positions/index.html` and
`sitemap.xml` and link it from the matching priority card on the home page.
Every factual claim needs a source in the page's Sources list.

## Workflow

- Commit directly to `main` for small edits — GitHub Pages redeploys
  automatically within a minute or two of a push.
- For anything you want to review before it's live, work on a branch and
  open a pull request instead.
