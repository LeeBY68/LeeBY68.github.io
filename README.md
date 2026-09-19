# leeby68.github.io

Boying Li's homepage — <https://leeby68.github.io>

Built with [al-folio](https://github.com/alshedivat/al-folio) (Jekyll).
Everything is one page: the navbar scrolls to sections rather than
linking to separate pages.

## Editing

| What | Where |
|---|---|
| Bio, research interests, page sections | `_pages/about.md` |
| Publications | `_bibliography/papers.bib` |
| News | `_news/update_*.md` (dates only order the list; they are not shown) |
| Experience, service, honors | `_data/cv.yml` |
| Navbar | `_data/navigation.yml` |
| Social links | `_data/socials.yml` |
| Figures | `assets/img/publication_preview/` |
| Fonts, spacing, section rules | `_sass/_custom.scss` |

### Publications

`selected = {true}` has no effect here — every active entry is listed.
To hide an entry, wrap it in `@comment{ ... }`.

`*` after an author's surname marks the corresponding author. Buttons come
from the link fields: `arxiv`, `html` (renders as "Paper"), `code`, `tools`,
`dataset`, `website`, `video`.

> BibTeX has no `%` comment. A `%` anywhere in this file makes the parser
> drop the entry **silently** — the build still succeeds. After editing,
> check that the expected number of papers is on the page.

### GitHub stars

Counts are baked into `_data/github_stars.yml` so visitors make no API
calls. CI refreshes them on every deploy. To refresh locally:

```bash
python3 bin/fetch-github-stars.py          # 60 requests/hour
GITHUB_TOKEN=ghp_... python3 bin/fetch-github-stars.py   # 5000/hour
```

Counts below `min_stars_shown` in `_config.yml` are not displayed.

## Local preview

```bash
bundle install
bundle exec jekyll serve --host 127.0.0.1 --port 4000
```

## Deploying

Push to `main`. The `deploy.yml` workflow builds the site and publishes
`_site` to `gh-pages`, which is what Pages serves.

## Theme overrides

These files shadow the ones al-folio ships in its gem. When upgrading
al-folio, compare them against upstream:

```
_layouts/about.liquid   _includes/header.liquid   _sass/_custom.scss
_layouts/bib.liquid     _includes/news.liquid     assets/css/main.scss
                        _includes/footer.liquid
                        _includes/gh_button.liquid
```

## History

The previous homepage is preserved on the `pre-al-folio` branch.
