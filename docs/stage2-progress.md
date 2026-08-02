# Stage 2 Progress: Notes And UI/UX Foundation

Status: active on the `stage-2` branch.

## Goal

Create a useful Notes section and establish a stable UI/UX foundation for the site. By the end of the stage, the site should have a deliberate visual direction, a recorded theme decision, consistent page types, and at least three published technical notes.

## Scope

Included:

- define the purpose and format of Notes;
- prepare and publish the first three notes;
- create the Notes section and add it to navigation when it has useful content;
- review and improve typography, spacing, navigation, page hierarchy, links, code blocks, mobile behavior, and keyboard use;
- decide whether to keep the custom root layouts or adopt a Hugo theme;
- verify the complete result and update project documentation.

Not included:

- Projects, Work With Me, or the first case study;
- a large branding exercise or decorative redesign;
- analytics, comments, newsletter integration, or new JavaScript features;
- editing generated files in `public/` or `resources/_gen/`.

## Current Baseline

- Root layouts and `assets/css/main.scss` render the active site.
- No Hugo theme is enabled; `themes/basic/` and `themes/ananke/` are inactive references.
- The site already supports responsive navigation, dark color-scheme preferences, readable content width, and visible keyboard focus.
- Posts and future Notes can initially share the existing list and single templates.
- The Notes navigation link exists only as commented template markup.

## Working Decisions

- Notes are short, durable technical entries focused on one practical point.
- A note should normally be 300–800 words and cite primary sources when it relies on external technical facts.
- Notes use `content/notes/_index.md` and one Markdown file per note.
- The Notes link stays hidden until at least three notes are publishable.
- The working hypothesis is to keep the custom root layouts because the site is small and already uses them. A theme switch requires a concrete maintenance or UX benefit.
- Do not maintain custom root templates and an enabled theme as competing implementations.

## Phase 1: Define The Notes Format

- [ ] Select the first three note topics from the technical core.
- [ ] Write a one-sentence reader takeaway for each topic.
- [ ] Confirm each topic is small enough for a note rather than a full post.
- [ ] Define front matter: `title`, `date`, `draft`, and `description` when useful.
- [ ] Decide whether notes need dates in list and single views; reuse the existing post date format where possible.
- [ ] Define a lightweight content checklist: one topic, practical conclusion, accurate code examples, and relevant primary-source links.

Deliverable: three scoped note briefs and a repeatable note format.

## Phase 2: Audit The Current UI/UX

- [ ] Review Home, About, Resume, Contact, Blog list, and a blog post at desktop and narrow mobile widths.
- [ ] Record issues in typography, spacing, content hierarchy, navigation, links, lists, code blocks, and long-form reading.
- [ ] Check keyboard navigation and focus visibility.
- [ ] Check light and dark color schemes for readable contrast and consistent surfaces.
- [ ] Identify which issues affect all page types and which need a Notes-specific template.
- [ ] Prioritize usability and readability issues before decorative changes.

Deliverable: a short, ordered UI/UX issue list with acceptance criteria.

## Phase 3: Decide The Visual And Theme Direction

- [ ] Define the intended visual character in a few constraints: simple, technical, readable, professional, and content-first.
- [ ] Compare the current custom implementation with the inactive theme options using the same criteria: accessibility, responsive behavior, content fit, maintenance cost, customization effort, and migration risk.
- [ ] Avoid building complete versions with multiple themes; prototype only the uncertain parts if inspection is insufficient.
- [ ] Choose one direction: keep and refine the root implementation, or enable and adapt one theme.
- [ ] Record the decision and its rationale in `docs/project-context.md`.
- [ ] Remove or defer obsolete alternatives only as a separate, explicit cleanup task.

Deliverable: one documented theme decision and one active implementation direction.

## Phase 4: Establish The Shared UI/UX Foundation

- [ ] Define or refine reusable color, spacing, typography, content-width, and surface variables in the active stylesheet.
- [ ] Make the header and navigation clear on desktop and mobile, including the future Notes link.
- [ ] Improve heading hierarchy, paragraph rhythm, lists, inline code, fenced code blocks, blockquotes, and horizontal overflow.
- [ ] Give list pages a clear title, entry hierarchy, date treatment, and spacing.
- [ ] Give single pages and posts consistent article width and metadata treatment.
- [ ] Preserve visible focus states and avoid interaction that depends only on hover or color.
- [ ] Keep changes compatible with system light and dark preferences.
- [ ] Use partial templates only when repeated markup creates a concrete maintenance problem.

Deliverable: consistent shared styles and templates for the existing site and Notes.

## Phase 5: Build And Publish Notes

- [ ] Create `content/notes/_index.md` with a concise description of the section.
- [ ] Create the first three note files with consistent front matter and stable URLs.
- [ ] Reuse the default list and single templates unless the UI/UX audit identifies a specific Notes requirement.
- [ ] Check summaries, dates, headings, code blocks, and external links in rendered output.
- [ ] Set `draft = false` only after each note passes the content checklist.
- [ ] Enable the Notes navigation link after all three notes are useful and publishable.
- [ ] Add a homepage link to Notes only if it improves discovery without duplicating navigation.

Deliverable: a public Notes section containing at least three reviewed notes.

## Phase 6: Integrate And Polish

- [ ] Review Home, Blog, Notes, top-level pages, and single content pages as one system.
- [ ] Confirm active navigation labels and ordering remain clear at narrow widths.
- [ ] Add internal links between related notes and the existing Hugo post where useful.
- [ ] Confirm that descriptions and Open Graph types remain appropriate for Notes pages.
- [ ] Fix only issues supported by the full-content review; record larger ideas for later stages.

Deliverable: a coherent site experience rather than an isolated Notes feature.

## Phase 7: Verification And Documentation

- [ ] Run a non-invasive production build:

  ```sh
  hugo --gc --minify \
    --destination /tmp/leedark-hugo-build \
    --cacheDir /tmp/leedark-hugo-cache
  ```

- [ ] Run `hugo server` and manually review representative desktop and mobile widths.
- [ ] Verify keyboard navigation, focus order, light and dark modes, long lines, and code-block overflow.
- [ ] Check `/notes/` and each note URL, plus Home, Blog, About, Resume, and Contact.
- [ ] Confirm no generated output was edited or added to the change set.
- [ ] Update `docs/project-context.md`, `docs/project-overview.md`, `docs/roadmap.md`, `docs/task-history.md`, and `README.md` where the completed behavior changes their current description.
- [ ] Review the complete diff before committing; keep commits focused and do not commit without explicit instruction.

Deliverable: verified implementation and documentation that describes the resulting site accurately.

## Parallel Writing Track

This runs throughout Stage 2 and should continue even while UI/UX work is in progress.

- Keep a private backlog with a working title, audience, takeaway, and supporting sources for each idea.
- Develop the first three notes independently enough that one blocked topic does not stop the section.
- Move a topic to Blog when it grows beyond one focused conclusion.
- Prefer original experience, tested examples, and explicit trade-offs over generic summaries.
- Review published material for opportunities to link Notes, Blog, and later Projects together.

## Definition Of Done

Stage 2 is complete when:

- at least three useful technical notes are published;
- Notes appears in navigation and renders correctly as a list and as individual pages;
- the active page types share a coherent visual hierarchy and reading experience;
- mobile layout, keyboard focus, light and dark modes, links, and code blocks have been reviewed;
- the theme direction is decided and documented, with only one active implementation;
- the production Hugo build succeeds;
- public project documentation matches the completed behavior;
- remaining UI/UX ideas are recorded as later refinements rather than hidden Stage 2 work.
