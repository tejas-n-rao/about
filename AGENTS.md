# Repository Guidelines

## Project Structure & Module Organization
This is a Jekyll-based academic site. Core configuration lives in `_config.yml` with structured data in `_data/`. Content collections are stored in `_pages/`, `_posts/`, `_projects/`, `_publications/`, `_talks/`, `_teaching/`, and `_portfolio/`. Layouts and shared UI fragments live in `_layouts/` and `_includes/`, while styling is split across `_sass/` and `assets/css/`. JavaScript sources are in `assets/js/`, with compiled output in `assets/js/main.min.js`. Static files belong in `images/` and `files/`. Content generation helpers live in `markdown_generator/` and `scripts/` (for example, CV JSON updates).

## Build, Test, and Development Commands
- `bundle install`: install Ruby/Jekyll dependencies.
- `bundle exec jekyll serve -l -H localhost`: run the site locally at `http://localhost:4000` with live reload.
- `docker compose up`: build/run the Docker-based local preview.
- `npm run build:js`: build the minified JS bundle.
- `npm run watch:js`: watch JS sources and rebuild on changes.
- `scripts/update_cv_json.sh`: refresh `_data/cv.json` from Markdown sources.

## Coding Style & Naming Conventions
Use Markdown files with YAML front matter. Follow the existing 2-space YAML indentation and keep keys consistent with existing pages. Use filename patterns like `_posts/YYYY-MM-DD-title.md` and `_talks/YYYY-MM-DD-name.md`. Keep new asset names lowercase with hyphens to match current conventions (for example, `images/profile.png`). SCSS changes should go in the appropriate partial under `_sass/` rather than editing compiled CSS.

## Testing Guidelines
There is no automated test suite. Validate changes by running the local Jekyll server and visually checking pages affected by your edits. For JavaScript changes, run `npm run build:js` and confirm the site still loads and navigates correctly.

## Commit & Pull Request Guidelines
Git history uses short, descriptive, title-case subjects without prefixes (for example, "New CV" or "Order Projects"). Keep commits focused and content-specific. PRs should include a short summary, the pages or collections touched, and screenshots for visual changes. Link related issues when applicable and note any required configuration changes.

## Security & Configuration Tips
Do not commit secrets or analytics keys. Configuration changes should be limited to `_config.yml` and `_data/` as needed, and you should verify any changes to navigation in `_data/navigation.yml` locally before pushing.
