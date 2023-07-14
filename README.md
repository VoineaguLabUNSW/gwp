# GWP Documentation

> **Warning**
> Documentation still under development

## Making Changes
The live branch is built automatically on commit, changes might take up to a minute.

In general, files and folders inside docs/ become pages in the site HOWEVER the "nav" section of mkdocs.yml must also be edited when adding or renaming a page or it will not appear. This was needed to prevent alphabetical ordering.

The sytax is a superset of markdown - you can see everything that is possible [here](https://squidfunk.github.io/mkdocs-material/reference/). Markdown tables are quite annoying, so I personally use a [HTML builder](https://www.tablesgenerator.com/html_tables) and tick "Do not generate CSS".

## Complex Changes
For intricate extensions that won't work if you get the whitespace wrong, you should:
    1. Clone this locally
    2. Install requirements.txt
    3. Commit and push changes when working, it will build automatically

```bash
# Testing, navigate to localhost:8000
mkdocs serve
```