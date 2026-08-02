# Project Guidance

## Project Context

- Purpose: Hugo-powered personal site and technical blog for `leedark.github.io`.
- Architecture: a static Hugo site with Markdown content, root Go templates, Hugo Pipes, SCSS, and GitHub Pages deployment.
- Primary tooling: Hugo Extended, Dart Sass, Markdown, Go templates, SCSS, and GitHub Actions.
- Important boundaries: preserve the source-first workflow, existing URLs and front matter, the inactive theme decision, and the generated-output rules below.

## Important Documents

Use the following documents according to the task. They are context sources, not replacements for
the user's latest explicit instruction.

- Current plan and priorities: `docs/roadmap.md`
- Project decisions and working context: `docs/project-context.md`
- Repository structure and commands: `docs/project-overview.md`
- Completed task history: `docs/task-history.md`
- AI-assisted development workflow: `docs/ai/ai-augmented-development-workflow.md`

- Read only documents relevant to the requested task.
- Treat `docs/roadmap.md` as the source of truth for current priority, active stage, and deferred work.
- Do not load every architecture, stage, or planning document by default.
- Russian/private documents under ignored paths are local working notes and should not be published or committed unless explicitly requested.

## Operating Contract

The user's latest explicit instruction takes precedence over the defaults in this file.

- Prefer small, reviewable changes.
- Inspect only files relevant to the task.
- Do not widen scope, redesign architecture, or add dependencies without a task-specific reason.
- Do not mix unrelated stages or tasks.
- Preserve user changes in the worktree; do not revert unrelated modifications.
- When the prompt names a working mode, apply the matching contract below.

## Resource And Cost Policy

- When model or reasoning selection is available, use the least expensive option that can reliably satisfy the task.
- Clarify scope and read relevant context before escalating model, reasoning, or tool usage.
- Do not use Fast mode, Max, Ultra, or subagents by default. Use them only when task latency, risk, or independent parallel work justifies the additional usage.
- Keep interactive Tutor and Pair Programmer turns short. Do not spend tokens polling while waiting for user input or implementation.
- For the detailed workflow, see `docs/ai/ai-augmented-development-workflow.md`.

## Working Modes

### Manager Mode

- Inspect relevant files before editing.
- Make the smallest focused change that satisfies the request.
- Preserve the existing project style and architecture.
- Run the narrowest relevant checks.
- Report changed files, checks, and remaining risks.
- Do not commit without explicit instruction.

### Documentation Mode

- Change only the requested documentation files.
- Do not change implementation files.
- Preserve technical meaning.
- Separate current behavior from planned behavior.
- Keep private or Russian working documents out of committed public documentation unless explicitly requested.

### Review Mode

- Inspect the requested change without editing files.
- List findings first and order them by severity.
- Include file and line references when possible.
- Mention test gaps and residual risks.

### Planning Mode

- Inspect only the context needed to prepare the plan.
- Define scope, stages, verification, and Definition of Done.
- Do not implement or edit files unless the user explicitly changes modes.

### Tutor Mode

- Treat the request as one interactive learning turn, not a persistent goal.
- Explain the concept and provide one focused exercise.
- Do not write the final implementation first.
- Do not edit files unless the user explicitly changes modes.
- Finish the response after the exercise and wait for the user.
- Waiting is not a blocker; do not poll the repository while waiting.
- Do not create a persistent goal or token budget.

### Pair Programmer Mode

- Treat the request as an interactive session, not a persistent goal.
- Let the user implement the first version.
- Before implementation, provide scoped guidance and acceptance criteria, then wait.
- Review the diff only after the user says it is ready.
- Suggest minimal targeted fixes instead of rewriting the solution.
- Waiting is not a blocker; do not poll the repository while waiting.
- Do not create a persistent goal or token budget.

### Book Or Source Study Mode

- Summarize concepts in original wording without copying large source fragments.
- Separate ideas into applicable now, deferred, or not relevant.
- Connect concepts to the current repository where useful.
- Do not implement source material until the user explicitly changes modes.

## Persistent Goals And Token Budgets

- Create a persistent Codex goal only when the user explicitly requests one.
- Set a token budget only when the user explicitly specifies it.
- A goal must be one bounded result that Codex can complete without waiting for user work.
- Do not use persistent goals for Tutor Mode or Pair Programmer Mode.
- Do not use pause as a substitute for ending an interactive turn.
- If the task requires user implementation or input, finish the current turn and wait normally.

## Verification Contract

- Run the narrowest relevant check first.
- Run the full test suite or production-style build when scope or risk justifies it.
- Report exact commands and results.
- Separate pre-existing failures from failures caused by the current change.
- If the environment prevents a check, explain the limitation and provide the local verification step.

For site-affecting changes, the usual production-style check is:

```sh
hugo --gc --minify
```

For a build that should not write to repository output directories:

```sh
hugo --gc --minify \
  --destination /tmp/leedark-hugo-build \
  --cacheDir /tmp/leedark-hugo-cache
```

## Completion Contract

After an implementation or documentation change, summarize:

- files changed;
- behavior or documentation changed;
- tests and checks run;
- failures, residual risks, or work intentionally left for later.

Do not create commits unless the user explicitly requests it.

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
- `themes/basic/` - local theme/reference files; not enabled.
- `themes/ananke/` - inactive Ananke theme source; not enabled.
- `.github/workflows/hugo.yaml` - GitHub Pages build and deploy workflow.
- `public/` and `resources/_gen/` - generated output/cache directories. Do not edit them by hand.

## Hugo And Theme Notes

- The active site is driven by root `hugo.toml`, root `layouts/`, and root `assets/`.
- No Hugo theme is currently enabled in `hugo.toml`; `theme = 'basic'` is commented out.
- Root templates override theme templates if a theme is enabled later.
- `assets/css/main.scss` is loaded from `layouts/_default/baseof.html`, compiled through Hugo Pipes, minified, and fingerprinted.
- The GitHub Pages workflow uses Hugo Extended `0.152.2`, Dart Sass, and runs `hugo --gc --minify`.
- Do not enable or replace a theme for a task that only needs a focused content, layout, metadata, or configuration change.

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
- Add descriptions when page-level metadata is relevant to the task.
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

## Project Boundaries

- Do not change the theme, layout, design, navigation, CSS, or generated output unless explicitly asked.
- Do not add `Projects`, `Notes`, or `Hire` navigation links before the corresponding public content exists.
- Keep current priorities and stage status in `docs/roadmap.md` rather than duplicating the backlog here.
- Do not edit `public/` or `resources/_gen/` directly.
- Do not create commits unless explicitly asked.
