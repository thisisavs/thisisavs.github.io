---
title: "Veo has an 8 second limit"
date: 2026-01-14
tags:
  - ai
  - video
  - veo
draft: false
---
*Co-authored with Claude (Anthropic)*

<!-- TIL: Google's Veo video generation has an 8 second limit per generation -->

Each Veo generation has a **hard limit** on duration:

| Model | Duration Options | Default |
|-------|------------------|---------|
| Veo 3 | 4, 6, or 8 seconds | 8 sec |
| Veo 2 | 5-8 seconds | 8 sec |

**This is not a bug, it's by design.** Video generation is compute-intensive, and quality degrades over longer clips.

**Workarounds for longer videos:**
1. Generate multiple 8-second clips with consistent style
2. Use Flow's **Scenebuilder** to arrange clips into a sequence
3. Use **Extend** to continue from a clip's last frame
4. Stitch clips in external editor (DaVinci Resolve, Premiere, etc.)

**Quick math:** A 2-minute video = 15 clips x 8 seconds

**Pro tip:** Use reference images ("Ingredients") across all clips to maintain character/style consistency.