---
title: "This Website"
date: 2026-01-11
tags:
  - hugo
  - hextra
  - web
  - meta
draft: false
description: "Building a simple personal website with Hugo, Hextra theme, and AI assistance"
images:
  - /project-images/personal-website-cover.png
imageStyle: "object-fit: contain; aspect-ratio: 16/9; background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%); padding: 2rem;"
---

![Celtic Owl Logo](/project-images/personal-website-cover.png)

*Co-authored with Claude (Anthropic)*

## What it is

The website you're looking at right now. A simple static site for my blog, TIL notes, and projects.

**Status:** 🚧 Work in Progress (perpetually, as websites tend to be)

## Why I built it

I had an old WordPress blog from 2014-2016 that I'd made private. Wanted a fresh start with:
- Full control over content
- No hosting costs
- Markdown-based workflow (write in Obsidian, publish via git)
- Something I could actually maintain

## Tech stack

| Component | Choice | Why |
|-----------|--------|-----|
| Generator | Hugo | Fast, simple, no runtime dependencies |
| Theme | Hextra | Clean docs/blog hybrid, Notion-like sidebar |
| Hosting | GitHub Pages | Free, deploys on push |
| Writing | Obsidian | Where I already take notes |

## The logo

The Celtic owl was generated using NanoBanana (Google Gemini). Went through several iterations - cute owls, geometric owls, tribal owls - before landing on this Celtic knotwork style that matches my aesthetic preferences.

## Features implemented

- [x] Homepage with recent posts and projects
- [x] Blog section (with migrated WordPress posts from 2014-2016)
- [x] TIL (Today I Learned) section
- [x] Projects section (you're looking at it)
- [x] Dark/light mode with adaptive favicon
- [x] Celtic owl logo in navbar

## Still to do

- [ ] Fill out About page properly
- [ ] Update /now page
- [ ] Set up GitHub Actions for auto-deploy
- [ ] Maybe add llms.txt support

*Yes, an AI helped write the description of the website that the AI helped build. It's turtles all the way down.*
