+++
date = '2026-08-03T01:01:02+03:00'
draft = false
title = 'Why I Built This Site with Hugo'
description = 'Why I chose Hugo for a simple, Git-based personal site built with Markdown and static generation.'
+++

## Introduction: Why I Started This Site

I have wanted to build a personal site and write publicly for a long time. The idea was always easy to postpone: there was more to learn, another project to finish, or some detail that needed to be improved first. At some point, waiting for the perfect starting point becomes another way of not starting.

This site is my way of taking that first step. I want it to be a practical home for my professional background, technical notes, and the projects I am learning from. It is not a finished portfolio or a promise that I already know everything. It is a place where I can document the work while I am still doing it.

## How I Came to Hugo

I had heard about Hugo for years, usually in the context of static sites and as an alternative to WordPress. I knew it was fast, but that description alone was not enough to make me try it. I did not have much time to explore it, and web development has never been my primary specialization.

For me, HTML, CSS, and visual layout have often felt less natural than backend code and system design. The part of a website that interests me most is usually the content: blog posts, articles, tutorials, documentation, and useful notes. I wanted a way to focus on that content without turning the first version of the site into a large frontend project.

Hugo seemed like a good place to begin because it offered a clear path from written content to a working website. I could write in Markdown, keep the source in Git, and let the generator produce the pages.

## How I Started Learning Hugo

My first step was to look at the [official Hugo documentation](https://gohugo.io/documentation/). It is useful as a reference, but I was looking for a more guided introduction: something that would explain not only individual features, but also how the pieces fit together in a real project.

That is why I returned to two books: [*Build Websites with Hugo*](https://pragprog.com/titles/bhhugo/build-websites-with-hugo/) by Brian P. Hogan and [*Hugo in Action*](https://www.manning.com/books/hugo-in-action/) by Atishay Jain. Reading them gave me a foundation for understanding content, layouts, configuration, themes, sections, and the build process.

I am still near the beginning of that journey. Hugo has many capabilities, and learning them can become overwhelming when every new feature suggests several more things to investigate. My current goal is not to master the whole tool before publishing anything. I want to move past that initial hesitation by connecting the learning process to a real site and a practical roadmap.

## Markdown, Git, and Static Generation

One reason Hugo feels approachable is that it builds on tools I already use.

Markdown is familiar to me. I use it for project documentation, technical notes, task lists, and other written material. It keeps the source readable and lets me concentrate on the structure and meaning of the text instead of writing HTML for every paragraph.

Git is another established part of my workflow. I use it for both personal and commercial projects, and I want to keep improving how I organize and review my changes. A personal site should benefit from the same discipline: the content and configuration should be visible in the repository, easy to change, and easy to recover.

Hugo connects these habits to static generation. In simple terms, the source files describe the content and the site structure, and Hugo turns them into HTML, CSS, and other publishable files. The result can be deployed without a runtime content management system. For someone who does not want to hand-code every page, this is a useful balance between control and simplicity.

## The Current Site Structure

The current site is intentionally small. It has a Home page, About, Resume, Contact, and a Blog section. The goal is to make those pages useful before adding more navigation or promising sections that do not have real content yet.

The repository follows Hugo's basic separation of responsibilities:

- `content/` contains pages and posts;
- `layouts/` describes how Hugo renders them;
- `assets/` contains styles processed by Hugo Pipes;
- `hugo.toml` contains site configuration;
- `public/` is generated build output, not a source directory.

This structure is simple enough to understand while still giving me room to grow. The site already works as a small professional base connected to my CV and public projects, but it is not finished. The content needs more refinement, and the site's visual design and user experience are areas I want to improve over time. Those improvements can happen incrementally instead of becoming a reason to delay the first real post.

## Future Writing Directions

The next articles should grow out of work I am already doing rather than from a fixed content calendar. I currently see three connected directions.

The first is Hugo and JAMstack: notes about learning the tool, building this site, and understanding the choices behind a small static website. The second is BookSocial and the wider work around Go web development, backend systems, and APIs. That series will document a real project as it develops, without trying to explain the entire system in one article.

The third direction is an AI-augmented Go developer workflow. I am interested in how AI tools can support learning, research, writing, and implementation while keeping the developer responsible for decisions and results. This is an area I want to explore through practice, not present as a finished formula.

These directions are a starting map, not a rigid publishing schedule. The site should follow the work: learn something, build something, reflect on it, and publish the useful part.

## Conclusion: Taking the First Step

Starting a project like this is difficult partly because there are so many possible directions. I could spend months comparing generators, redesigning the interface, planning future sections, or trying to understand every Hugo feature before publishing a single article.

That would miss the point. A personal site does not have to start as a large technical project. Hugo lets me take a first step with familiar tools such as Markdown, Git, and static generation. I can learn the rest as the site grows.

This post is that first step. The site is still small, the roadmap will change, and there is much more to learn. But changes and new challenges are easier to approach once they become concrete work. I do not need a perfect plan before I begin; I need a useful starting point and the willingness to continue.
