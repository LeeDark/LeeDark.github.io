# Project Overview

This is a Hugo personal site and blog published at `https://leedark.github.io/`.

This document is a quick technical orientation. For working decisions and project background, see `docs/project-context.md`. For planned work, see `docs/roadmap.md`.

## Organization

- `hugo.toml` is the main site configuration.
- `content/` contains Markdown pages and posts.
- `layouts/` contains the active Hugo templates used by the site.
- `assets/css/main.scss` contains the active stylesheet compiled by Hugo.
- `static/` is for files that should be copied directly to the generated site.
- `themes/basic/` and `themes/ananke/` are present, but the root config does not currently enable a theme.
- `public/` is generated site output and should not be edited manually.
- `resources/_gen/` is Hugo-generated cache output and should not be edited manually.

## Running Locally

Start the local development server:

```sh
hugo server
```

Preview draft content too:

```sh
hugo server -D
```

Build the production site:

```sh
hugo --gc --minify
```

The GitHub Pages workflow uses Hugo Extended `0.164.0` and builds with `hugo --gc --minify`.

## Adding Content

Add blog posts in `content/posts/`. The default archetype creates front matter with:

```toml
+++
date = '{{ .Date }}'
draft = true
title = '{{ replace .File.ContentBaseName "-" " " | title }}'
+++
```

Set `draft = false` when a post is ready to publish.

Top-level pages currently live directly in `content/`, including `about.md`, `contact.md`, and `resume.md`.

## Styles And Assets

The active stylesheet is `assets/css/main.scss`. It is referenced from `layouts/_default/baseof.html`, compiled through Hugo Pipes, minified, and fingerprinted.

Use `static/` for assets that should be copied as-is into the published site. Use `assets/` for files Hugo should process.

## Project Conventions

- Keep changes small and easy to review.
- Preserve the current simple layout and navigation unless a task explicitly asks for design changes.
- Do not edit generated output in `public/` or `resources/_gen/`.
- Run a Hugo build after template, style, config, or content changes when possible.
