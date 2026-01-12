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
| Switching themes later | Easy enough | Content is portable, just config/front matter changes |

## User Context
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
- [ ] Set up GitHub Actions for auto-deploy
- [ ] **Verify:** Site live at `thisisavs.github.io`

### Phase 2: Core Pages
- [ ] About page
- [ ] /now page
- [ ] **Verify:** Pages render correctly

### Phase 3: TIL Section
- [ ] Create TIL content type
- [ ] Add first TIL entries
- [ ] TIL listing page
- [ ] **Verify:** New .md file + push = new TIL appears

### Phase 4: TIB (Projects)
- [ ] Projects section
- [ ] Add a project or two
- [ ] **Verify:** Projects display nicely

### Phase 5: Blog
- [ ] Blog section with listing
- [ ] First post
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

## Git Cheatsheet
```bash
git add .
git commit -m "your message"
git push
```

---

## Status
**Current Phase:** 1 - Foundation
**Next Step:** Create GitHub repo and deploy

### Resume Instructions
```bash
cd E:\claude_code_home\personal_website
hugo server
```
Site runs at http://localhost:1313/

### Setup Notes
- Using git submodule for Hextra (no Go required)
- Theme installed at `themes/hextra`
