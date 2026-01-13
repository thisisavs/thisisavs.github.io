# Personal Website - Project Plan

## Goal
Simple, professional personal website. Markdown files → git push → live site. Free.

## Stack
**Hugo + GitHub Pages + Hextra theme**

## Key Decisions (for any AI picking this up)

| Decision | Choice | Why |
|----------|--------|-----|
| Static vs Dynamic | Static (Hugo) | Free hosting on GitHub Pages, no server needed |
| Why not Django/Python | Overkill | User knows Python but Django requires paid hosting, databases, maintenance |
| Theme | Hextra | TIL/notes-focused aesthetic, Notion-like sidebar nav, simpler than Congo |
| Theme install method | Git submodule | Go not installed, avoids extra dependencies |
| Section layouts | `type: blog` | TIL/Blog/Projects use blog-style listing (content + posts below), not docs-style sidebar |
| Content workflow | Obsidian → copy to Hugo | User writes in Obsidian, manually copies to content/ when ready |
| Logo/Favicon | Celtic owl (PNG) | Matches user's Odin tattoo aesthetic; owl = wisdom; PNG over SVG (complex design) |
| Favicon dark mode | Separate PNGs + media queries | Hextra's SVG approach didn't work; custom favicons.html partial |

## User Context
- Name: A V S Sai Babu (goes by Sai)
- Profession: Market research analyst (NOT software engineer)
- GitHub: thisisavs
- Beginner with web dev, knows markdown and git (rusty)
- Wants: About, /now, TIL, TIB (projects), Blog, Principles pages
- Priority: Clean professional look, simplicity, no cost
- See `ideas for website.md` for full feature wishlist
- See `Sai_offline_inputs.md` for additional feature ideas

---

## Phases

### Phase 1: Foundation
- [x] Install Hugo
- [x] Create new Hugo site
- [x] Pick a clean theme (Hextra via git submodule)
- [x] Basic config (name, description)
- [x] Create GitHub repo (`thisisavs.github.io`)
- [ ] Set up GitHub Actions for auto-deploy *(on hold - user wants to do later)*
- [ ] **Verify:** Site live at `thisisavs.github.io`

### Phase 2: Core Pages
- [x] About page (with profile photo, side-by-side layout)
- [x] /now page (template created)
- [x] **Verify:** Pages render correctly

### Phase 3: TIL Section
- [x] Create TIL content type (`type: blog` in _index.md)
- [x] TIL listing page
- [ ] Add first real TIL entries
- [ ] **Verify:** New .md file + push = new TIL appears

### Phase 4: TIB (Projects)
- [x] Projects section (structure done)
- [ ] Add real projects
- [ ] **Verify:** Projects display nicely

### Phase 5: Blog
- [x] Blog section with listing
- [ ] First real post
- [ ] **Verify:** RSS feed works

### Phase 6: Extras
- [ ] Principles page
- [ ] Stuff I like page
- [ ] Admonymous link

---

## Parked Ideas
- Personal/Professional toggle
- Letters to AI concept
- LLMs.txt support with Human/Machine toggle (like parallel.ai) - see Sai_offline_inputs.md
- Custom domain (later, when worth paying)

---

## Content Structure

```
content/
├── _index.md              ← Homepage (landing page)
├── about.md               ← About page
├── now.md                 ← /now page
├── til/
│   ├── _index.md          ← TIL listing (type: blog)
│   └── *.md               ← Individual TILs
├── blog/
│   ├── _index.md          ← Blog listing (type: blog)
│   └── *.md               ← Blog posts
└── projects/
    ├── _index.md          ← Projects listing (type: blog)
    └── *.md               ← Project pages

static/
├── favicon.svg            ← Owl favicon (adaptive light/dark)
└── *.jpg, *.png           ← Images (reference as /filename.png)

layouts/
└── index.html             ← Custom homepage layout
```

## Front Matter Template
```yaml
---
title: "Your Title"
date: 2026-01-12
tags:
  - tag1
  - tag2
draft: false
---
```

---

## Git Cheatsheet
```bash
git add .
git commit -m "your message"
git push
```

---

## Status
**Current Phase:** Design complete! Ready for content and deployment.
**Next Steps:**
1. Fill in About page placeholders (`content/about.md`) - AI Tool Stack section added
2. Fill in /now page (`content/now.md`)
3. Write first real TIL/blog post
4. Set up GitHub Actions when ready to deploy
5. Push to GitHub and go live!

See also: `E:\claude_code_home\Sai_todo_personal_website.md` for user's content tasks

### Completed (Jan 13 2026 Session - Owl Logo & Polish)
- [x] **Celtic Owl Logo** - Generated using NanoBanana (Gemini image gen)
  - Explored multiple styles: cute, geometric, tattoo, tribal, Norse/Celtic
  - Final choice: Celtic knotwork owl (#4 from tribal/Norse grid)
  - Matches user's Odin tattoo aesthetic
- [x] **Favicon system** (PNG-based, light/dark mode):
  - `favicon.ico`, `favicon-16x16.png`, `favicon-32x32.png` (dark owl, light bg)
  - `favicon-dark-16x16.png`, `favicon-dark-32x32.png` (white owl, for dark mode)
  - Custom `layouts/_partials/favicons.html` with media queries
- [x] **Navbar logo** - Owl beside site title (28x28px), auto-switches light/dark
- [x] **About page** redesigned:
  - Title changed to "Hi, I'm Sai" (not "About")
  - Photo with side-by-side layout (180x180px)
  - Added "My AI Tool Stack" placeholder section
- [x] Generated images saved in `E:\claude_code_home\generated_images\`

### Completed (Jan 12 2026 Session)
- [x] New homepage layout (custom `layouts/index.html`)
  - Hero section: "Hi, I'm Sai." title + intro + photo (180px, side-by-side)
  - Recent Blog + Recent TIL columns (auto-populated from content)
  - Projects cards grid (auto-populated)
- [x] Separate About page (`content/about.md`)
- [x] Updated navbar: Home | About | Now | TIL | Projects | Blog
- [x] Photo size tuned: started at 200px → 120px (too small) → 180px (final)

### Key Files Modified This Session
```
static/
├── owl_logo.png           ← Main logo (dark owl)
├── owl_logo_dark.png      ← Dark mode logo (white owl)
├── favicon.ico
├── favicon-16x16.png
├── favicon-32x32.png
├── favicon-dark-16x16.png
├── favicon-dark-32x32.png
└── apple-touch-icon.png

layouts/_partials/
└── favicons.html          ← Custom override with light/dark media queries

hugo.toml                  ← Added navbar.logo config
content/about.md           ← Redesigned with photo + AI stack section
```

### Resume Instructions
```bash
cd E:\claude_code_home\personal_website
hugo server
```
Site runs at http://localhost:1313/

### Setup Notes
- Using git submodule for Hextra (no Go required)
- Theme installed at `themes/hextra`
- Repo: https://github.com/thisisavs/thisisavs.github.io
- Profile photos in `static/` (using Sai_Photo_Square.jpg)
- Logo generation: Used NanoBanana skill (Google Gemini) for owl designs

### Open Questions
- Cloudflare Pages vs GitHub Pages? (user noted this - worth exploring)
- GitHub Actions primer/references needed