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

## Stage 2: Notes And UI/UX Foundation — Active

Goal: establish a lightweight technical-note format and a stable visual foundation for the site.

Action items:

1. Collect at least three concrete note ideas before creating `content/notes/`.
2. Keep each note to one practical point, roughly 300–800 words, with sources for external technical claims.
3. Publish at least three notes before adding Notes to the navigation.
4. Review typography, spacing, content width, navigation, mobile behavior, keyboard focus, link treatment, code blocks, and the visual hierarchy of pages, posts, lists, and notes.
5. Decide whether to continue with the custom root layouts and styles or adopt a Hugo theme. Record the decision and avoid keeping two competing implementations active.
6. Treat the result as the stable UI/UX foundation; later stages may refine it when real content reveals a concrete issue.

Definition of done: Notes has useful content, the main page types are visually consistent and usable, and the theme direction is explicitly decided.

## Stage 3: Work With Me

Goal: make the kinds of professional problems to discuss clear without duplicating the Contact page.

Action items:

1. Create `content/work-with-me.md` or `content/hire.md` only after the positioning text can be specific.
2. Describe four to six relevant areas: Go backend services, APIs and integrations, telecom or messaging systems, profiling, observability, production debugging, or backend documentation.
3. Include brief “good fit” and “not a good fit” guidance, then point to the existing contact methods.
4. Add navigation only after the content is concrete and reviewable.

Definition of done: a recruiter, engineering manager, or potential collaborator understands which conversations are useful to start.

## Stage 4: Projects

Goal: add a Projects page that explains selected repositories as portfolio evidence, not just as links.

Action items:

1. Create `content/projects/_index.md`. A section page supports the initial portfolio page and leaves room for project-specific case studies.
2. Start with three or four selected repositories: `go-microservices-starter`, `go-web-labs`, `go-testing-zoo`, and this site where appropriate.
3. For each entry, explain its purpose, the engineering skills it demonstrates, its stack, its current status, and provide a GitHub link.
4. Keep the selection intentional: exclude weak, obsolete, or duplicate repositories.
5. Link Projects from the homepage and navigation only when the page has useful content.

Definition of done: a visitor can understand why each listed repository matters without opening it first.

## Stage 5: Public Release And Experience Review

Goal: validate the site as a coherent public portfolio and improve the experience where it affects comprehension, reading, or navigation.

Action items:

1. Manually review `/`, `/about/`, `/resume/`, `/projects/`, `/posts/`, `/contact/`, and any completed Notes or Work With Me pages.
2. Check mobile readability, navigation clarity, keyboard focus, heading hierarchy, link labels, and the visibility of the strongest next action on each page.
3. Verify GitHub, LinkedIn, email, RSS, sitemap, robots, canonical URLs, and social previews; add favicon and a 404 page if still missing.
4. Run `hugo --gc --minify` and, when useful, a build with the production base URL.
5. Confirm the Stage 2 UI/UX and theme decisions against the completed content, then make any focused corrections found during review.

Definition of done: the site is accurate, usable on mobile and keyboard, free of placeholder content, and ready to link from external profiles.

## Stage 6: First Case Study

Goal: show engineering thinking with one focused write-up.

Action items:

1. Pick one strong subject from a project or system: service architecture, queues and messaging, observability, graceful shutdown, profiling, or performance investigation.
2. Publish it as a project page or a blog post, using a clear structure: problem, context, constraints, architecture, implementation notes, trade-offs, and next improvements.
3. Link it from Projects and, where useful, add a return link from the relevant repository later.
4. Focus on decisions and evidence rather than presenting the project as a finished product.

Definition of done: one project demonstrates both implementation skill and engineering judgement.

## Stage 7: First Month Of Publishing

Goal: establish a sustainable technical publishing habit after release rather than treating the site as a one-time portfolio task.

Action items:

1. Publish about one small technical item per week: a note, short post, case-study update, or project decision.
2. Maintain a private idea backlog without turning every idea into a commitment.
3. Keep early topics in the technical core: Go and backend services, messaging and reliability, observability and performance, Hugo as a secondary meta-track, and AI-assisted development for engineers.
4. Add internal links between projects, posts, notes, About, and Resume when a new piece becomes a strong portfolio artifact.
5. At the end of the month, review which topics were practical to write and useful to readers; use that evidence to select two or three content tracks.
6. Improve UI/UX only in response to concrete reading or navigation issues; do not begin a large redesign during this period.

Definition of done: the site has a small but living body of technical work, including several short pieces and one stronger engineering write-up.

## Parallel Track: Writing And Blog Development

This track runs alongside Stages 2–7. It prevents stage-specific site work from delaying the development of the blog itself.

1. Keep a private backlog of post and note ideas, with a working title, audience, one-sentence takeaway, and supporting project or source.
2. Draft and publish one real technical post when a topic needs more than a note; favor practical experience, decisions, and trade-offs over generic tutorials.
3. Use Notes for small conclusions and Blog for longer articles and case studies; link related material in both directions.
4. Review the backlog and published work monthly, then keep, combine, or drop topics based on genuine interest and evidence.
5. Avoid adding personal, finance, philosophy, or broad lifestyle topics to the main technical site until the technical direction is established.

## Deferred Decisions

These are useful, but not required for the current stage.

- Consider partial templates for repeated head, navigation, or footer markup after the current structure becomes limiting.
- Consider a broader visual redesign only after the content base and experience review show a specific need.
