# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal website for Sai Babu (market research analyst). Static site using Hugo + Hextra theme, hosted on GitHub Pages.

**Live URL:** https://thisisavs.github.io/

## Commands

```bash
# Development server (hot reload)
hugo server
# → http://localhost:1313/

# Production build
hugo
# → outputs to public/

# Check theme submodule status
git submodule status
```

No npm/yarn/pip needed. Hugo is the only dependency.

## Architecture

### Content Structure
```
content/
├── _index.md          # Homepage (uses layouts/index.html)
├── about.md           # About page (partially filled)
├── now.md             # /now page
├── lists.md           # Curated lists (placeholder)
├── principles.md      # Personal principles (placeholder)
├── til/               # Today I Learned (type: blog)
├── blog/              # Blog posts (type: blog)
└── projects/          # Project portfolio (type: blog)
```

Each section uses `type: blog` in `_index.md` for blog-style listings.

### Custom Layouts
- `layouts/index.html` - Homepage with hero, recent content columns, project cards
- `layouts/_partials/favicons.html` - Custom favicon loader with light/dark mode media queries

### Static Assets
- Logo: `owl_logo.png` (light), `owl_logo_dark.png` (dark)
- Profile photo: `Sai_Photo_Square.jpg` (180x180px)
- Favicons: PNG-based system with dark mode variants (`favicon-dark-*.png`)

### Theme
Hextra v0.11.1 installed as git submodule in `themes/hextra/`. No Go required.

## Key Decisions

| Decision | Choice | Why |
|----------|--------|-----|
| Theme install | Git submodule | No Go dependency |
| Section layouts | `type: blog` | Blog-style listing, not docs-style sidebar |
| Favicon dark mode | Separate PNGs + media queries | Hextra's SVG approach didn't work |
| Logo | Celtic owl PNG | Matches user's aesthetic preference |

## Front Matter

```yaml
---
title: "Post title"
date: 2026-01-12
lastmod: 2026-01-12
tags:
  - tag1
draft: false
description: "Optional summary for listings"
---
```

- `lastmod`: Update this when editing a post. Displayed as "Last updated on [date]" at bottom of post.
- See `front-matter-templates.md` for full templates.

## User Context

- Owner: A V S Sai Babu (goes by "Sai")
- Technical level: Beginner with web dev, knows markdown and git
- Priority: Simplicity, no cost, clean professional look
- See `Sai_offline_inputs.md` for user's idea backlog

## Current Status (as of 2026-01-31)

### What's Done
- ✅ Homepage with hero, recent TIL/Blog columns, project image cards (6-column grid)
- ✅ Celtic owl logo + favicon system (light/dark mode)
- ✅ TIL section with 8 entries (numbered prefixes for ordering)
- ✅ Blog section with 5 migrated WordPress posts + 1 new essay ("Let there be light")
- ✅ Projects section with 4 image cards
- ✅ Tags display enabled (on listings + TOC sidebar)
- ✅ Co-author disclaimers standardized (top of content, after cover images)
- ✅ "Last updated" date enabled (`displayUpdatedDate = true` in hugo.toml)
- ✅ About page partially filled (photo, AI tool stack, links, card nav)
- ✅ Lists page created (placeholder with template)
- ✅ Principles page created (placeholder with template)

### What's Next (User's Tasks)
1. **About page** - finish filling in real content (current job, past experience, side projects)
2. **Now page** - fill in content (`content/now.md`)
3. **Lists page** - fill in curated lists (books, tools, advice)
4. **Principles page** - fill in personal principles
5. **GitHub Actions** - user learning, will set up auto-deploy
6. **Add `lastmod` to existing TIL/Blog posts** - for transparency on older content

### Parked Ideas
- LLMs.txt support with Human/Machine toggle (see `Sai_offline_inputs.md`)

## Session Notes (2026-01-31)

### New Blog Post: "Let there be light"
- Essay on AI as creative renaissance, parallels to Medici patronage and "Fiat Lux"
- File: `content/blog/2026-01-29-let-there-be-light.md`
- Tags: essays, renaissance, ai, optimism, build, world models
- Date: 2026-01-23 (original writing date), lastmod: 2026-01-29

### Enabled "Last Updated" Display
- Added `displayUpdatedDate = true` to `[params]` in `hugo.toml`
- Uses Hextra's built-in `last-updated.html` partial
- Shows "Last updated on [date]" at bottom of blog/TIL posts
- Requires `lastmod` field in front matter (Hugo standard field)
- Existing posts without `lastmod` won't show the label (no breaking change)

### Between-Session Changes (by user)
- About page updated: photo, AI tool stack, links, card navigation to other sections
- New pages created: `lists.md` (curated lists), `principles.md` (personal principles) - both placeholders
- Navbar updated: added Principles and Lists links (visible in about page card nav)

---

## Recent Session Notes (2026-01-17)

### WordPress Migration
Migrated posts from `thisisavssai.wordpress.com`:
- XML export: `C:\Users\avssa\Downloads\avssaibabu.WordPress.2026-01-17.xml`
- Media export: `C:\Users\avssa\Downloads\media-export-68049103-from-0-to-294/`
- Posts have note at top: "*Originally published on my old WordPress blog...*"

### Image Cards Implementation
- Projects page uses Hextra `{{< cards >}}` shortcode with `image` param
- Homepage uses same styling via custom template (copies Hextra's card.html logic)
- Images stored in `static/project-images/`
- Use `imageStyle="object-fit: cover; aspect-ratio: 16/9;"` for consistency

### Projects Added
| Project | Status | Cover Image |
|---------|--------|-------------|
| Competitor News Digest | Completed | `/project-images/competitor-news-digest-cover.png` (from GitHub repo) |
| Owl Babies | WIP | `/project-images/owl-babies-cover.jpg` |
| Let Claude Be | Ongoing | `/project-images/let-claude-be-cover.png` (generated via NanoBanana) |
| This Website | WIP | `/project-images/personal-website-cover.png` |

### Cover Image Generation
Used NanoBanana skill to generate "Let Claude Be" cover:
```bash
python ~/.claude/skills/nanobanana/scripts/generate.py "prompt" -a 16:9 -r 2K -o "path/to/output.png"
```
Theme: Raspberry Pi + emergence patterns (cellular automata, fractals), dark background with glowing cyan/amber elements.

## Session Notes (2026-01-18 - Part 2)

### Tags Display Enabled
Added to `hugo.toml`:
```toml
[params.blog.list]
  displayTags = true

[params.toc]
  displayTags = true
```
- Tags now appear on blog/TIL listing pages
- Tags appear in TOC sidebar on individual posts
- Clicking a tag goes to `/tags/{tag-name}/` showing all posts with that tag
- Did NOT add Tags to navbar (user preference - can access via clicking tags on posts)

### Co-author Disclaimer Pattern
For AI-assisted content, add disclaimer line:
- **TIL/Blog posts** (no cover image): Right after front matter `---`
- **Projects** (with cover image): After the cover image, before first heading

Example for projects:
```markdown
---
title: "Project Name"
...
---

![Cover](/project-images/cover.png)

*Co-authored with Claude (Anthropic)*

## First Heading
```

### GitHub Actions Resources Shared
User wants to learn GitHub Actions for deployment. Recommended:
- [GitHub Docs Quickstart](https://docs.github.com/actions/quickstart)
- [freeCodeCamp Guide](https://www.freecodecamp.org/news/learn-to-use-github-actions-step-by-step-guide/)
- [Microsoft Learn Module](https://learn.microsoft.com/en-us/training/modules/introduction-to-github-actions/) (video)

---

## Session Notes (2026-01-18 - Part 1)

### Added Competitor News Digest Project
- Source: https://github.com/thisisavs/agents_capstone
- Date: 2025-12-11 (Google AI Agents course capstone)
- Cover image downloaded from repo's `assets/agenticFlow.png`
- Multi-agent system using Google ADK for competitor intelligence

### Project Front Matter Pattern
Each project needs these fields for proper display on homepage and projects page:
```yaml
images:
  - /project-images/cover-image.png
imageStyle: "object-fit: contain; aspect-ratio: 16/9; background: #ffffff; padding: 0.5rem;"
```
- `images` array: Used by homepage template to display card image
- `imageStyle`: Custom CSS for image display (contain vs cover, background color, etc.)

### Homepage Project Cards
- Updated `layouts/index.html` to match Hextra's card.html shortcode
- Uses `safeURL` and `safeCSS` filters for proper rendering
- Grid columns: Changed from 2 → 4 → 6 for smaller, more compact cards
- Current setting: `--hextra-cards-grid-cols: 6`
