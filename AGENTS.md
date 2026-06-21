# Project Guidance

## Project Description

This repository is a Hugo-powered personal site and blog for `leedark.github.io`. It contains portfolio-style pages, a posts section, custom root layouts, and SCSS compiled through Hugo Pipes.

## Repository Structure

- `hugo.toml` - main Hugo site configuration. The deployed site uses this root config.
- `content/` - Markdown content pages and posts.
  - `content/_index.md` - home page content.
  - `content/about.md`, `content/contact.md`, `content/resume.md` - top-level pages.
  - `content/posts/` - blog posts.
- `layouts/` - active root Hugo templates for the site.
  - `layouts/_default/baseof.html` - shared HTML shell and navigation.
  - `layouts/_default/single.html` - single page/post rendering.
  - `layouts/_default/list.html` - section/list rendering.
  - `layouts/index.html` - home page layout.
- `assets/css/main.scss` - active site stylesheet compiled by Hugo Pipes.
- `static/` - static files copied directly into the generated site. Currently empty.
- `archetypes/default.md` - default front matter for new content, with `draft = true`.
- `themes/basic/` - local theme/reference theme files. The root config currently has `theme = 'basic'` commented out.
- `themes/ananke/` - Ananke theme source/submodule-like directory. It is present but not enabled by the root config.
- `.github/workflows/hugo.yaml` - GitHub Pages build and deploy workflow.
- `public/` and `resources/_gen/` - generated output/cache directories. Do not edit these by hand.

## Hugo And Theme Notes

- The active site is driven by root `hugo.toml`, root `layouts/`, and root `assets/`.
- No theme is currently enabled in `hugo.toml`; `theme = 'basic'` is commented out.
- Root templates override theme templates if a theme is enabled later.
- `assets/css/main.scss` is loaded from `layouts/_default/baseof.html` with Hugo Pipes, minified, and fingerprinted.
- The GitHub Pages workflow uses Hugo Extended `0.152.2`, Dart Sass, and runs `hugo --gc --minify`.

## Common Commands

- Local development server:

  ```sh
  hugo server
  ```

- Local development server including draft content:

  ```sh
  hugo server -D
  ```

- Production build:

  ```sh
  hugo --gc --minify
  ```

- Production-style build with an explicit base URL:

  ```sh
  hugo --gc --minify --baseURL "https://leedark.github.io/"
  ```

## Content Editing Rules

- Add blog posts under `content/posts/`.
- Use Hugo front matter consistent with `archetypes/default.md`: `title`, `date`, and `draft`.
- New archetype-created content starts as `draft = true`; publish by explicitly changing it to `false`.
- Do not edit generated files in `public/` or `resources/_gen/`.
- Do not rewrite existing posts or pages unless explicitly asked.
- Preserve existing URLs, front matter, dates, and draft status unless the task requires a change.

## Blog Style Rules

- Keep posts in Markdown with clear headings and short sections.
- Use descriptive titles and stable dates.
- Prefer concise, plain language.
- Link to primary sources when referencing external technical facts.
- Keep code examples fenced with a language identifier when practical.
- Avoid large formatting-only rewrites that make content history harder to review.

## Rules For Future Codex Tasks

- Make small, focused changes scoped to the user request.
- Explain the plan before editing files.
- Do not rewrite posts unless explicitly asked.
- Do not change the theme, layout, design, navigation, CSS, or generated output unless explicitly asked.
- Run the safest relevant Hugo build/check command after changes when possible, usually `hugo --gc --minify`.
- Stop after each logical step and summarize changes for review.
- Do not create commits unless explicitly asked.
- Do not edit `public/` or `resources/_gen/` directly.
- Respect user changes in the worktree; do not revert unrelated modifications.
