# AGENTS.md

## Repository Goal

This repository is a collection of technical guides, notes and tutorials aimed at developers. Content is bilingual (Spanish and English) and each topic directory contains one or more `.md` files explaining useful concepts or procedures for day-to-day work.

The content is intended to be published online using **GitHub Pages** and **MkDocs**, so that anyone can access the guides comfortably from a browser.

## How to Contribute

- Keep content under language folders: `docs/es/` and `docs/en/`.
- Each new topic should go in its own directory inside both languages (e.g. `docs/es/tmux/` and `docs/en/tmux/`).
- One or more Markdown files can be created inside each topic directory.
- Home indexes live at `docs/es/README.md` and `docs/en/README.md` and must list available topics for each language.
- When adding a new topic, update both language indexes and add the corresponding translated article.

## Publishing

**MkDocs** with the Material theme and `mkdocs-static-i18n` will be used to generate the static site, and **GitHub Pages** will host it. The MkDocs configuration is defined in `mkdocs.yml` in the project root.
