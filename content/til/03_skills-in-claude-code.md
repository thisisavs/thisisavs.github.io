---
title: "Skills in Claude Code"
date: 2026-01-13
tags:
  - ai
  - claude
  - claude-code
  - productivity
draft: false
---
*Co-authored with Claude (Anthropic)*

<!-- TIL: Claude Code supports custom "skills" - reusable prompts/workflows -->

# Skills are awesome!!

You can give Claude super powers by giving it 'skills' alsmost matrix like. Claude can learn to use new tools, workflows when we add all the necesary directions in the skills folder in the prescribed manner.

## Skill Structure

Skills live in `~/.claude/skills/<skill-name>/` with this structure:

```
~/.claude/skills/
└── my-skill/
    ├── SKILL.md          # Required: skill definition
    └── scripts/          # Optional: helper scripts
        └── helper.py
```

## SKILL.md Syntax

The `SKILL.md` file uses YAML front matter + markdown body:

```markdown
---
name: my-skill
description: What this skill does (shown in /help)
allowed-tools: Bash, Read, WebFetch   # Optional: restrict tools
---

# Instructions for Claude

Write detailed instructions here...
```

**Key fields:**
- `name`: The slash command name (e.g., `my-skill` → `/my-skill`)
- `description`: Shown when listing available skills
- `allowed-tools`: Comma-separated list of tools Claude can use (optional, defaults to all)

Once created, invoke with `/<skill-name>` in Claude Code.

Also Claude itself can help in building skills if you provide the right documentation, source and best practice guides for the task at hand. 

Here are some of the skills i created and use:
- **`/nanobanana`** - Generate and edit images using Google Gemini (NanoBanana Pro). Professional-quality image generation with text rendering, character consistency, and style transfer.
- **`/veo`** - Generate videos using Google Veo 3.1. Supports cinematic prompts, dialogue, sound effects, and multi-shot sequences.
- **`/wind-down`** - End-of-session checklist. Reviews accomplishments, updates documentation, and ensures nothing gets lost.

**Get them here:** [github.com/thisisavs/skills](https://github.com/thisisavs/skills)
