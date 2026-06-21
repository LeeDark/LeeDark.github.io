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
