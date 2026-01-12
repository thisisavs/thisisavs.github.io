# Front Matter Templates for Hugo

Copy the relevant template when creating new content.

---

## TIL Post

```yaml
---
title: "What I learned about X"
date: 2026-01-12
tags:
  - tag1
  - tag2
draft: true
---

Your content here...
```

---

## Blog Post

```yaml
---
title: "Post title"
date: 2026-01-12
tags:
  - tag1
description: "Optional short summary for listings"
draft: true
---

Your content here...
```

---

## Project Page

```yaml
---
title: "Project Name"
date: 2026-01-12
tags:
  - python
  - web
description: "One-line description"
draft: true
---

## What it is

## Why I built it

## How it works

## Links
- [GitHub](https://github.com/thisisavs/project)
- [Live demo](https://example.com)
```

---

## Notes

- **date**: Use `YYYY-MM-DD` format
- **draft: true**: Hidden from site. Change to `false` when ready to publish.
- **tags**: Used for filtering/browsing. Keep lowercase, use hyphens for multi-word (`machine-learning`)
- **description**: Optional. Shows in listings if provided, otherwise Hugo uses first ~70 words.

## Where to save

| Content type | Save to |
|--------------|---------|
| TIL | `content/til/your-file.md` |
| Blog | `content/blog/your-file.md` |
| Project | `content/projects/your-file.md` |

## Filename tips

- Use lowercase with hyphens: `my-first-til.md`
- Keep it short but descriptive
- No spaces or special characters
