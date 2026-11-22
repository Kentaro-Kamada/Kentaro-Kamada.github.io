# Repository Guidelines

## Project Structure

This is Kentaro Kamada’s Quarto website. Edit the home, profile, and research pages in the root-level `.qmd` files. Add posts under `blog/posts/`, where `_metadata.yml` provides shared settings. The blog listing lives in `blog/index.qmd`.

Use `_quarto.yml` for site-wide configuration, `styles.css` for custom styling, and `reference.bib` for citations. Site images live in `images/` and blog graphics in `blog/images/`. Shared R code lives in `utilities/`, and `renv.lock` records R dependencies. Quarto stores frozen results in `_freeze/` and writes the rendered site to the ignored `_site/` directory.

## Build and Local Checks

- `quarto check` reports the local Quarto setup and available execution engines.
- `quarto preview` serves the site locally and refreshes it as files change.
- `quarto render` builds the full site. `quarto render research.qmd` renders a specific page.

Preview and render can execute embedded analysis. Inspect the affected code and obtain explicit approval before running commands that would execute analysis. Use the existing environment and get approval before installing dependencies or changing it.

There is no dedicated test suite or coverage target. For site changes, review the rendered pages for working navigation, links, figures, and citations. Check the blog listing when changing post metadata.

## Style and Naming

Match the surrounding page’s language and heading structure. Follow nearby posts for YAML front matter, including `title`, `date` in `YYYY-MM-DD` format, and `categories`. Indent nested YAML with two spaces. Keep existing filenames stable because they determine published URLs.

## Commits and Pull Requests

Recent commits use short Japanese summaries, such as `researchページを更新`. Describe the affected page or post in the commit subject. In a pull request, summarize the affected pages and checks performed, link related issues when available, and include screenshots for visible layout changes. Pushes to `main` trigger publication to GitHub Pages.

## Data Handling

Keep `01_rawdata/` and `02_middle/` out of searches, diffs, and renders. Use synthetic fixtures for checks that need data.
