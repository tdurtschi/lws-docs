# Lake Wingra Software Knowledge Base

Published at: https://tdurtschi.github.io/lws-docs/

## Structure

```
mkdocs/
  mkdocs.yml       # Site config and nav
  docs/
    index.md       # Home page
    *.md           # All content pages (flat)
    img/           # Images used by content pages
docs/              # Built output (served by GitHub Pages)
```

## Local setup

Install MkDocs (one time):

```sh
python3 -m venv .venv
source .venv/bin/activate
pip install mkdocs
```

Activate the virtualenv in future sessions:

```sh
source .venv/bin/activate
```

## Build

```sh
pushd mkdocs; mkdocs build -d ../docs; popd
```

## Dev server

```sh
cd mkdocs && mkdocs serve
```

## GitHub Pages Deployment

Pushes to `main` trigger the deploy workflow (`.github/workflows/deploy.yml`), which builds with MkDocs and deploys the `gh-pages` branch automatically:

```sh
git push
```

The site will be available at: https://tdurtschi.github.io/lws-docs/
