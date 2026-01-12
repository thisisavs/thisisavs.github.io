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

## User Context
- Name: A V S Sai Babu (goes by Sai)
- GitHub: thisisavs
- Beginner with web dev, knows markdown and git (rusty)
- Wants: About, /now, TIL, TIB (projects), Blog, Principles pages
- Priority: Clean professional look, simplicity, no cost
- See `ideas for website.md` for full feature wishlist

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
- Machine-readable version for LLMs
- Custom domain (later, when worth paying)

---

## Content Structure

```
content/
├── _index.md              ← About (homepage)
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
└── *.jpg, *.png           ← Images (reference as /filename.png)
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
**Current Phase:** 2-5 structure complete, needs real content
**Next Steps:**
1. Fix About page layout (current table hack has borders showing - need Hextra docs to do it properly)
2. Fill in About page placeholders (`content/_index.md`)
3. Fill in /now page (`content/now.md`)
4. Write first real TIL
5. Set up GitHub Actions when ready to deploy

### Known Issue
About page side-by-side layout not working properly. Tried:
- Inline styles (stripped by Hugo)
- `<style>` block (stripped)
- Custom CSS in `assets/css/custom.css` (not loading)
- Tailwind classes with `hx:` prefix (not applied)
- HTML table (works but has border styling from theme)

**Solution:** Check Hextra docs for proper way to add custom layouts or use shortcodes.

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
