# Charles Chi Xu Academic Website

This repository builds and deploys [charlesxuuu.github.io](https://charlesxuuu.github.io), Charles Chi Xu's academic website. It is based on the Academic Pages Jekyll theme, with active public content kept small and example theme content archived for future reference.

## Site Structure

- `_config.yml`: site metadata, author profile, collection settings, plugins, and build configuration.
- `_pages/`: public standalone pages. The current live pages are the homepage, publications page, sitemap, and 404 page.
- `_publications/`, `_talks/`, `_teaching/`, `_portfolio/`, `_posts/`: content collections kept for future expansion.
- `images/`: live profile, favicon, and site image assets.
- `files/`: public downloadable files.
- `assets/`, `_sass/`, `_includes/`, `_layouts/`: theme styles, scripts, templates, and reusable components.
- `_examples/academic-pages-samples/`: archived Academic Pages sample content and assets. Use these as references when adding new sections, but they are not published.

## Local Development

Install Ruby, Bundler, and Node.js, then install dependencies:

```bash
bundle install
npm install
```

Run the site locally:

```bash
bundle exec jekyll serve -l -H localhost
```

The site is available at `http://localhost:4000`. Restart the server after changing `_config.yml`.

Build the static site before publishing larger changes:

```bash
bundle exec jekyll build
```

Rebuild minified JavaScript after editing `assets/js/_main.js` or plugin scripts:

```bash
npm run build:js
```

## Adding Content

Add new pages under `_pages/` and enable their links in `_data/navigation.yml` when they should appear in the header. Add publications, talks, teaching entries, portfolio items, or posts to their matching collection directories using the archived examples as front matter references. Store PDFs and other public downloads in `files/`; store page images in `images/`.

The `markdown_generator/` scripts and notebooks can help generate publication or talk markdown from TSV files.

## Deployment

GitHub Actions builds the site with Jekyll and deploys it to GitHub Pages on pushes to `master`. Use the `wip` branch for current work and keep `handcraft` as the clean baseline branch.

## Maintenance

Keep public content personal to this site. Do not reintroduce template demo pages into published directories unless they are rewritten as real content. After structural changes, run `bundle exec jekyll build` and inspect the affected pages locally.
