# blrdroidcommunity.github.io
Landing page for blrdroid meetup

## Structure

The site is built with [Jekyll](https://jekyllrb.com/), which GitHub Pages runs automatically — no build step to set up yourself.

- **`index.md`** — all the page copy (headings, paragraphs, button labels/links), as YAML front matter. **This is the file to edit for text changes.** Paragraph fields are plain markdown, so you can use blank lines for new paragraphs, `**bold**`, `[links](url)`, etc.
- `_layouts/default.html` — the page structure/design (Liquid template). Edit this only when changing layout, not copy.
- `assets/css/theme.css` — the "Organic" design-system stylesheet (colors, type, components) — the design source of truth, not page-specific.
- `assets/css/site.css` — page-specific layout CSS (section spacing, grid) that arranges the design-system tokens for this page.
- `assets/img/` — local images.
- `design/` — source design canvas (Claude Design) the site was originally built from; excluded from the published site, kept for reference only.

## Editing text

Open `index.md` and change the value under the relevant key, e.g.:

```yaml
about:
  heading: Built by developers, for developers
  body: |-
    We're a bunch of Android engineers, hobbyists, and students in Bangalore...

    Sessions are free, informal, and open to anyone curious about Android...
```

`body` fields use YAML's `|-` block style so multi-line/multi-paragraph markdown just works — keep the text indented under the key.

## Build locally

Requires Ruby ≥ 3.0 (macOS's built-in Ruby is too old — install a current one with `brew install ruby` if needed).

```sh
bundle install       # first time only, installs Jekyll + deps from the Gemfile
bundle exec jekyll serve
```

Then open `http://localhost:4000`. The server auto-rebuilds on save, so edits to `index.md` show up on refresh. Use `bundle exec jekyll build` instead of `serve` to just generate the static output into `_site/` without running a server.

## Deploy (GitHub Pages)

This is a `<org>.github.io` repo, so GitHub Pages serves it automatically:

1. Push to `main`.
2. In **Settings → Pages**, set **Source** to "Deploy from a branch", branch `main`, folder `/ (root)` (usually the default already).
3. GitHub builds the Jekyll site and publishes it to `https://blrdroidcommunity.github.io/`, usually within a minute or two of each push.
