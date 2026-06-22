# Repository Guidelines

## Project Structure & Module Organization

This repository is a GitHub Pages Jekyll site based on Academic Pages. Site-wide settings live in `_config.yml`, navigation and author data in `_data/`, reusable HTML in `_includes/`, page templates in `_layouts/`, and Sass partials in `_sass/`. Main pages are in `_pages/`; content collections use `_posts/`, `_publications/`, `_talks/`, `_teaching/`, and `_portfolio/`. Put static images in `images/`, downloadable PDFs in `files/`, and front-end assets in `assets/`. The `markdown_generator/` scripts help create publication and talk markdown from TSV files.

## Build, Test, and Development Commands

- `bundle install`: install Ruby and Jekyll dependencies from `Gemfile`.
- `bundle exec jekyll serve -l -H localhost`: run the site locally at `http://localhost:4000` with live reload.
- `bundle exec jekyll build`: build the static site into `_site/`; use this before pushing layout or config changes.
- `npm install`: install JavaScript build dependencies.
- `npm run build:js`: rebuild `assets/js/main.min.js` from plugin scripts and `assets/js/_main.js`.
- `docker build -t jekyll-site .` then `docker run -p 4000:4000 --rm -v ${PWD}:/usr/src/app jekyll-site`: run in Docker.

## Coding Style & Naming Conventions

Use two-space indentation for YAML, HTML, Markdown front matter, and Sass. Name dated content with prefixes, for example `_posts/YYYY-MM-DD-title.md` and `_publications/YYYY-MM-DD-paper-title.md`. Prefer lowercase, hyphenated slugs for URLs and filenames. Edit source Sass in `_sass/` and JavaScript in `assets/js/`; do not hand-edit generated `_site/` output.

## Testing Guidelines

There is no formal unit test suite. Treat `bundle exec jekyll build` as the required validation step. For visual or navigation changes, also run the local server and check affected pages, menus, images, and downloads in a browser. If JavaScript changes are made, run `npm run build:js` and verify `assets/js/main.min.js`.

## Commit & Pull Request Guidelines

Recent history uses short imperative messages such as `Update about.md` and `Create jekyll.yml`; follow that pattern and name the main file or area changed. Pull requests should include a brief summary, affected pages or collections, validation performed, and screenshots for visible layout changes. Link related issues when applicable.

## Security & Configuration Tips

Do not commit secrets, private drafts, or unpublished PDFs unless they are meant to be public. Keep profile fields, analytics IDs, and deployment settings in `_config.yml` accurate.
