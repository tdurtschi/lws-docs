# Lake Wingra Software Knowledge Base

Published at: https://tdurtschi.github.io/lws-docs/site/

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

## Deploy
Note: Build the application before deploying to either environment.

### Staging (GitHub Pages)

Commit and push the updated `docs/` directory to deploy to GitHub Pages:

```sh
git add docs/
git commit -m "Update docs"
git push
```

The site will be available at: https://tdurtschi.github.io/lws-docs/site/

### Production (Azure)

To deploy to production Azure Blob Storage:

```sh
az storage blob upload-batch -s docs/ -d '$web' --account-name $ACCOUNT_NAME --overwrite
```

Use `--overwrite` to ensure all files (including `index.html`) are updated.