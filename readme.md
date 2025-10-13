# Lake Wingra Software Knowledge Base

[Click Here](https://tdurtschi.github.io/lws-docs/site/) to browse knowledge base.

## Local setup 

First, install mkdocs:
```sh
pip install mkdocs
```

To install / activate a virtual env:
```sh
# install (only required once)
python3 -m venv .venv

# activate (required whenever starting a new session)
source .venv/bin/activate
```

Also see https://www.mkdocs.org/getting-started/

## Quick build

`pushd mkdocs; mkdocs build -d ../docs; popd;`

## Dev Mode
`mkdocs serve`