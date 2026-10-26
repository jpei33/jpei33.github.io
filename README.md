# jpei33.github.io

Personal site built with [Quarto](https://quarto.org). Free and open source; hosting is free on GitHub Pages.

## One-time setup

1. Install Quarto: `brew install --cask quarto` on Mac, or the installer from quarto.org on Windows.
2. Create a public GitHub repo named **`jpei33.github.io`** and push this folder to its `main` branch.
3. In the repo: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
4. Push. The site appears at https://jpei33.github.io within a couple of minutes.

## Writing

```bash
quarto preview          # live-reloading local preview
```

New post: copy `posts/_templates/project.qmd` or `concept.qmd` to `posts/YYYY-MM-slug/index.qmd`.

- `draft: true` keeps a post off the published site. The source is still visible in a public repo, so keep anything truly private in a separate private repo or local folder.
- Mark hand-waving inline with `<!-- GAP: ... -->`, then sweep them into `_private/gaps.md` weekly and delete them before publishing (HTML comments are visible in page source):

```bash
grep -rn "GAP:" posts/
```

- Delete `draft: true` to publish.

## Layout

```
_quarto.yml        site config
index.qmd          post listing
_private/gaps.md   running gap log (gitignored, never published)
about.qmd
posts/
  _templates/      not rendered (leading underscore)
  2026-10-retrieval-eval/
.github/workflows/publish.yml   renders and deploys on push to main
```
