# Task History

## Task 1: Homepage Slogan

Replaced the placeholder homepage slogan in `layouts/index.html` with a short description of the site focused on Go backend engineering, web services, reliability, observability, and practical software engineering.

## Task 2: Site Title

Updated the site title in `hugo.toml` from `Lee's Personal & Blogging` to `Lee's Personal Blog` so the homepage, page titles, and footer read more naturally.

## Task 3: Homepage Front Matter

Added TOML front matter to `content/_index.md` with `date`, `draft = false`, and `title = 'Home'` to make the homepage metadata consistent with the other top-level content pages.

## Task 4: Recent Post Dates

Updated the homepage recent-posts list in `layouts/index.html` to show each post date using the same `YYYY-MM-DD` format already used by the blog list template.

## Task 5: Site Metadata

Added a default site description in `hugo.toml` and expanded the shared HTML head in `layouts/_default/baseof.html` with computed page titles, description metadata, canonical URLs, and basic Open Graph tags.

## Task 6: Task History

Created this task history document in `docs/task-history.md` to keep a concise record of completed site improvements.

## Task 7: Basic Typography

Added simple typography spacing in `assets/css/main.scss` for `main`, headings, paragraphs, and lists so pages and posts have clearer vertical rhythm.

## Task 8: Content Width

Changed the `.container` maximum width in `assets/css/main.scss` from `1100px` to `820px` to improve blog readability on wider screens.

## Task 9: Nav And Footer Colors

Moved nav and footer colors in `assets/css/main.scss` into `--surface` and `--surface-fg` variables, including dark-mode values.

## Task 10: Keyboard Focus

Added a visible `a:focus-visible` outline in `assets/css/main.scss` so keyboard navigation is easier to follow.

## Task 11: About And Resume Content

Updated `content/about.md` and `content/resume.md` with CV- and GitHub-based content focused on Go backend engineering, telecom/messaging experience, production observability, selected projects, education, and languages.

## Task 12: Contact And Home Copy

Updated `content/contact.md`, `content/_index.md`, and `layouts/index.html` with professional contact and homepage copy, added GitHub to contact links, and kept the homepage slogan only in the layout to avoid duplicated positioning text.

## Task 13: Baseline Roadmap

Added `docs/roadmap.md` to capture Stage 1 action items for the Hugo baseline, branch workflow, generated-output rules, deferred theme decisions, and documentation follow-ups.

## Task 14: Project Context

Added `docs/project-context.md` for project decisions, branch workflow, source-of-truth rules, theme status, content direction, and verification guidance. Updated `docs/project-overview.md` to link overview, context, and roadmap responsibilities.

## Task 15: Portfolio README

Added a root `README.md` as a public-facing repository overview for the personal Hugo site, including site purpose, visible engineering choices, tech stack, local commands, workflow notes, and links to supporting docs.
