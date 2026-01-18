---
title: "Veo vs Flow - what's the difference?"
date: 2026-01-13
tags:
  - ai
  - video
  - veo
  - flow
draft: false
---
*Co-authored with Claude (Anthropic)*

<!-- TIL: The difference between Google Veo and Flow for video generation -->

**Veo** is Google's AI video generation model. You give it a text prompt (and optionally reference images), and it generates a video clip. Think of it as the "engine" that creates video from nothing.

**Flow** is Google's video editing and orchestration platform. It's where you arrange, sequence, and refine Veo-generated clips. Key features:
- **Scenebuilder**: Arrange multiple clips into a coherent sequence
- **Extend**: Continue a video from its last frame
- **Ingredients**: Upload reference images for character/style consistency

**The relationship:**
- Veo = generates individual clips (4-8 seconds each)
- Flow = the workspace where you stitch clips together, extend them, and apply edits

**When to use what:**
- Need a single short clip? Use Veo directly (via API or Claude Code `/veo` skill)
- Building a longer video with multiple scenes? Generate clips with Veo, arrange in Flow