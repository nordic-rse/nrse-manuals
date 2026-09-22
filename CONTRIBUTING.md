# Contributing to the Nordic-RSE manuals

This repo is built into a documentation site with [Sphinx](https://www.sphinx-doc.org/), published to <https://nordic-rse.github.io/nrse-manuals/>.

Sphinx is a documentation generator: it takes source files (here, Markdown via the [MyST](https://myst-parser.readthedocs.io/) parser) and builds them into a navigable site (HTML, plus PDF/epub in our case). It's configured via `conf.py` in this repo. See the [Sphinx documentation](https://www.sphinx-doc.org/en/master/) for more, or the [MyST syntax guide](https://myst-parser.readthedocs.io/en/latest/syntax/syntax.html) for the Markdown extensions it supports (e.g. the `{toctree}` and admonition blocks used in this repo).

## index.md vs README.md

`index.md` is a symlink to `README.md` — they are the same file on disk, not two copies. Sphinx needs a file named `index.md` as its root page (`master_doc = 'index'` in `conf.py`), while GitHub renders `README.md` as the repo's landing page; the symlink lets one file serve both without duplicating content. `conf.py` excludes `README.md` from the Sphinx build itself, so it isn't processed twice. In practice: just edit `README.md` (or `index.md`, it's the same file), and both stay in sync automatically.

## Adding a new page

1. Add a new `.md` file at the repo root.
2. Add it to the relevant `{toctree}` block in `README.md` — a page not listed in a toctree won't appear in the built site's navigation, even though the file exists. (This has bitten us before — several pages in this repo were created without being added to a toctree.)

## Building locally

```
pip install -r requirements.txt
make html
```

Open `_build/html/index.html` in a browser. `make dirhtml` produces the same output but matches the structure used for the live site more closely.

`make gh-pages` (used by CI) additionally builds the single-page HTML, PDF, and epub versions, which requires a full LaTeX install (`make gh-pages-dependencies`) — you generally don't need this for local editing.

### Without `make`

`make html` is just a wrapper around `sphinx-build`; you can call it directly instead:

```
sphinx-build -b html . _build/html
```

(`-b` selects the builder, e.g. `dirhtml` or `epub` instead of `html`.) Or, since `requirements.txt` also installs [`sphinx-autobuild`](https://github.com/sphinx-doc/sphinx-autobuild), get a live-reloading dev server:

```
sphinx-autobuild . _build/html
```

## CI checks

- **Sphinx build** (`.github/workflows/sphinx.yml`): builds the site on every push/PR, and deploys to `gh-pages` on push to `main`.
- **Spellcheck** (`.github/workflows/spellcheck.yml`): runs [`misspell`](https://github.com/client9/misspell) on every push and fails the build on errors. Run `bin/misspell -error *` locally if you want to check before pushing.

## Conventions used in this repo

- Prefer linking to the canonical page over repeating its content — several pages here link to each other (or out to [nordic-rse.org](https://nordic-rse.org)) rather than duplicating text, to avoid the copies drifting out of sync.
- Public-facing content (who we are, how to join, event info) belongs on nordic-rse.org; this repo is the organizer/board-facing "how we actually do this" side — see the note at the top of [README.md](README.md).
- Where we don't actually know how something is done in practice, say so with a `TODO:` note rather than guessing or leaving it blank.
