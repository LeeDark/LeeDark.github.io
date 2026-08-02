# LeeDark.github.io

Source code for my personal Hugo site and technical blog:

<https://leedark.github.io/>

The site is a small professional home for my Go backend work, writing, resume, and public project notes. It is intentionally simple: static pages, clear navigation, readable typography, and a build pipeline that produces a fast GitHub Pages site.

## What This Repository Shows

- A Hugo-based personal site with custom root layouts.
- Markdown-driven content for top-level pages and posts.
- SCSS compiled through Hugo Pipes, minified, and fingerprinted.
- GitHub Pages deployment through GitHub Actions.
- A source-first workflow where generated output is not edited by hand.

## Tech Stack

- Hugo / Hugo Extended
- Markdown content
- Go templates
- SCSS with Hugo Pipes
- GitHub Pages
- GitHub Actions

## Site Structure

- `hugo.toml` - main Hugo configuration.
- `content/` - Markdown pages and blog posts.
- `layouts/` - active Hugo templates.
- `assets/css/main.scss` - active stylesheet.
- `static/` - static files copied directly into the generated site.
- `.github/workflows/hugo.yaml` - GitHub Pages build and deploy workflow.

Generated directories such as `public/` and `resources/_gen/` are not source of truth and should not be edited manually.

## Running Locally

Start the development server:

```sh
hugo server
```

Preview drafts too:

```sh
hugo server -D
```

Build the production site:

```sh
hugo --gc --minify
```

## Development Notes

The production-oriented site is developed from `main`. A separate `book` branch is used for Hugo learning exercises, and useful work from that branch is moved back into `main` only as focused changes.
Stage work uses focused short-lived branches; `stage-2` is preparing the Projects section.

No Hugo theme is currently enabled in `hugo.toml`. The active site uses the root `layouts/` and `assets/` files.

## Documentation

- `docs/project-overview.md` - repository structure and common commands.
- `docs/project-context.md` - working decisions, branch workflow, and source-of-truth rules.
- `docs/roadmap.md` - current roadmap and deferred decisions.
- `docs/task-history.md` - concise history of completed site tasks.

Stage 1 public readiness is complete. The current focus is Stage 2: a Projects section that explains selected repositories as portfolio evidence and can grow into project case studies.
