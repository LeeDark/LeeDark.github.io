# Project Context

This document records working context and decisions that are useful when changing the site. For file layout and commands, see `docs/project-overview.md`. For planned work, see `docs/roadmap.md`.

## Purpose

This repository is the source for the public personal site at `https://leedark.github.io/`.

The site should work as a small professional home page and technical writing base. The current direction is Go backend engineering, reliable services, telecom and messaging systems, observability, production performance, and practical software engineering.

## Working Branches

- `main` is the production-oriented branch for the real personal site.
- `book` is a Hogan learning branch for Hugo exercises and experiments.
- `stage-2` is the short-lived working branch for the Projects stage; merge it into `main` only after the stage work is reviewed.
- Useful work from `book` should move into `main` only as focused, reviewed changes.
- Jain book work is kept in the separate `LeeDark/acme-corporation` repository.

Do not merge broad learning-branch changes into `main` just because they are related to Hugo.

## Source Of Truth

The active site is driven by:

- `hugo.toml`
- `content/`
- `layouts/`
- `assets/`
- `static/`

Generated output is not source of truth:

- `public/`
- `resources/_gen/`

Do not edit generated output directly. Change source files and rebuild instead.

## Theme Decision

The repository currently contains `themes/basic/` and `themes/ananke/`, but no theme is enabled in `hugo.toml`.

The active templates and styles are the root `layouts/` and `assets/` files. Treat the theme directories as inactive until a specific task decides whether to remove them, keep them as references, or introduce a real theme workflow.

## Content Direction

Current public pages:

- Home
- About
- Resume
- Blog
- Contact

Near-term content priorities:

- complete the Projects section with useful project descriptions;
- use `content/projects/_index.md` so focused case studies can be added under the section later;
- add a first case study after Projects establishes the portfolio context;
- add Notes only when there are several short note ideas ready.

Avoid promising empty sections from the homepage or navigation.

## Editing Principles

- Keep changes small and easy to review.
- Prefer content-only changes unless the task explicitly asks for layout, design, CSS, or config work.
- Preserve URLs, front matter, dates, and draft status unless the task requires a change.
- Keep public-facing copy professional, specific, and grounded in real source material such as the CV and public GitHub profile.
- Add abstractions, partials, or theme structure only when the current root layout structure becomes limiting.

## Verification

For site-affecting changes, run a Hugo build when possible:

```sh
hugo --gc --minify
```

For docs-only changes, a full site build is usually unnecessary. If a non-invasive build is useful, write generated output outside the repository:

```sh
hugo --gc --minify --destination /tmp/leedark-hugo-build --cacheDir /tmp/leedark-hugo-cache
```
