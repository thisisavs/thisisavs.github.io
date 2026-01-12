---
title: "Building a personal website with Claude Code and Hugo"
date: 2026-01-12
tags:
  - hugo
  - claude-code
  - web
draft: true
---

I wanted a simple personal website: markdown files, git push, live site. No databases, no paid hosting, no complexity.

## The stack I landed on

**Hugo + GitHub Pages + Hextra theme**

- **Hugo**: Static site generator. Turns markdown into HTML. Fast, no runtime dependencies.
- **GitHub Pages**: Free hosting for static sites. Push to repo → site updates.
- **Hextra**: Clean theme with good defaults for TIL/docs-style sites.

## Key learnings

**Hugo themes can be installed via git submodule** - avoids needing Go installed. Just:
```bash
git submodule add https://github.com/imfing/hextra.git themes/hextra
```

**Section pages use `_index.md`** - this file provides the intro text for a section. Individual posts in that folder appear as listings below it.

**`type: blog` in front matter** - switches from docs-style (sidebar nav) to blog-style (content + listings). Important for TIL/blog sections.

**Images go in `static/`** - reference them as `/filename.png` (leading slash = root of static folder).

**Front matter is required** - every markdown file needs the `---` block at top with at least title and date.

## What Claude Code handled well

- Scaffolding the Hugo site structure
- Configuring the theme
- Explaining which files do what
- Git operations (init, commit, push)
- Debugging layout issues (like switching to blog-style listings)

## What I still need to do myself

- Fill in actual content (About page, /now page)
- Write real posts
- Set up GitHub Actions for auto-deploy
- Eventually: custom domain

## The workflow now

1. Write markdown in Obsidian
2. Add front matter, copy to `content/til/` or `content/blog/`
3. `git add . && git commit -m "message" && git push`
4. Site updates (once GitHub Actions is set up)

Simple. Which was the whole point.