# Roadmap

This roadmap tracks practical work for the Hugo personal site. It is intentionally scoped to source files and project workflow, not generated output.

## Current Baseline

- The production site is developed from `main`.
- The `book` branch is used as a Hogan learning branch for Hugo exercises and experiments.
- The Jain book work lives in the separate `LeeDark/acme-corporation` repository.
- The active site uses root `hugo.toml`, `content/`, `layouts/`, and `assets/`.
- `public/` and `resources/_gen/` are generated output and should not be edited manually.
- `themes/basic/` and `themes/ananke/` are present but not enabled.

## Stage 1: Baseline And Public Readiness — Complete

Goal: keep the site simple, understandable, and safe to change while preparing it for a first solid public version.

Action items:

1. Keep the Hugo mental model explicit: `content/` supplies pages and posts, `layouts/` renders HTML, `assets/` contains processed styles, `static/` contains copied files, and `public/` is build output.
2. Keep `main` focused on the real personal site and avoid merging broad learning-branch changes into it.
3. Move only useful, reviewed work from `book` into `main`, preferably as small cherry-picks or manual focused edits.
4. Replace or unpublish the placeholder first post before treating the blog as public-ready.
5. Run a Hugo build after content, layout, style, or config changes when possible.
6. Do not edit `public/` or `resources/_gen/` directly.
7. Add an explicit page description to the homepage so its meta description does not fall back to the full page summary.
8. Refine `og:type` in `baseof.html`: use `article` for blog posts and `website` for the homepage, regular pages, and section pages.

Completed outcomes:

- Replaced the placeholder post with `Why I Built This Site with Hugo`.
- Added an explicit homepage description and context-appropriate Open Graph types.
- Updated the GitHub Pages workflow to Hugo Extended `0.164.0` and Dart Sass `1.102.0`.

## Stage 2: Projects — Active

Goal: add a real Projects page that explains selected repositories as portfolio evidence, not just as links.

Action items:

1. Create `content/projects/_index.md`. A section page supports the initial portfolio page and leaves room for project-specific case studies.
2. Add a short list of selected projects with purpose, stack, status, and GitHub links.
3. Link Projects from the homepage and navigation only when the page has useful content.

## Stage 3: First Case Study

Goal: show engineering thinking with one focused write-up.

Action items:

1. Pick one project or system topic.
2. Write a case study with problem, constraints, implementation notes, trade-offs, and next improvements.
3. Link the case study from Projects or Blog.

## Stage 4: Notes

Goal: add a lightweight format for short technical notes.

Action items:

1. Create `content/notes/` only after there are at least a few concrete note ideas.
2. Keep notes short and focused on one technical point.
3. Add navigation only after the section has real content.

## Deferred Decisions

These are useful, but not required for the current stage.

- Evaluate `themes/`: remove unused themes, keep them as references, or plan a real theme step later.
- Consider partial templates for repeated head, navigation, or footer markup after the current structure becomes limiting.
