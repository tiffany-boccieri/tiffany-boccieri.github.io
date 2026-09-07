# tiffany-boccieri.github.io

Campaign site for Tiffany Boccieri for Laguna Hills City Council, District 4.
Plain static HTML/CSS — no build step, no framework.

Served by GitHub Pages directly from the `main` branch, at the custom domain
in [`CNAME`](CNAME).

> **Note:** the bio/issues copy and footer disclosure line in `index.html`
> are placeholders — review and fact-check before this goes live, and confirm
> the exact required disclosure wording with the campaign treasurer / FPPC
> filer.

## Local preview

No dependencies needed — just Python's built-in server:

```bash
python -m http.server 8000
```

Then open http://localhost:8000 in a browser. Stop the server with Ctrl+C.

## Structure

- `index.html` — the whole site (single page)
- `style.css` — all styles
- `assets/` — images
- `CNAME` — custom domain for GitHub Pages

## Workflow

- Commit directly to `main` for small edits — GitHub Pages redeploys
  automatically within a minute or two of a push.
- For anything you want to review before it's live, work on a branch and
  open a pull request instead.
