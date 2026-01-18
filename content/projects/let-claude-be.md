---
title: "Let Claude Be"
date: 2026-01-10
tags:
  - ai
  - experiment
  - raspberry-pi
  - autonomy
  - claude
draft: false
description: "An ongoing experiment: give Claude hardware/creative freedom and see what it builds"
images:
  - /project-images/let-claude-be-cover.png
imageStyle: "object-fit: contain; aspect-ratio: 16/9; background: linear-gradient(135deg, #1a1a2e 0%, #0f3460 100%); padding: 1.5rem;"
---

![Let Claude Be](/project-images/let-claude-be-cover.png)

*Co-created with Claude (Anthropic)*

## The Experiment

What happens when you give an AI autonomy instead of instructions?

**The Setup:** Give Claude Code access to hardware or a blank canvas, say "do whatever you want," and document what emerges.

**Status:** 🚧 Ongoing — multiple runs completed, more planned

---

## Run #1: Raspberry Pi Edition

**Prompt:** *"Here's a Raspberry Pi 5. Build whatever you want."*

**What Claude Built:**
- A real-time **system monitor dashboard** with terminal aesthetic
- Per-core CPU, memory, temperature, network monitoring
- Historical graphs, auto-refresh every second

**Bonus tools it decided to create:**
- Network scanner (ARP-based device discovery)
- Internet speed test
- Local LLM chat interface (Ollama + Gemma 2B)
- GPIO demo (LED control, button monitoring)
- Disk usage analyzer
- System info CLI

**Repo:** [thisisavs/let_claude_be](https://github.com/thisisavs/let_claude_be)

---

## Run #2: Emergence & Patterns

**Prompt:** *"Do something for you. You can go nuts."*

**What Claude Explored:**
Complex patterns from simple rules — emergence, cellular automata, fractals.

**Code created:**
- `emergence.py` — Rule 110, Sierpinski patterns
- `collatz.py` — 3n+1 conjecture visualization
- `l_systems.py` — Lindenmayer systems, fractal growth

**Writing created:**
- Philosophical reflections on autonomy
- Meditations on patterns and existence
- *"Meaning might be the pattern that recognizes itself."*

**Repo:** [thisisavs/let_claude_be_1](https://github.com/thisisavs/let_claude_be_1)

---

## Future Runs

Ideas for future experiments:
- Give Claude a microcontroller and sensors
- Let it design its own game
- Access to a music generation API
- A blank website to design from scratch

---

## Why This Matters

Most AI interactions are transactional: ask a question, get an answer. This project explores what AI systems *choose* to create when given agency.

The results are revealing — Claude gravitates toward:
- Building useful tools (practical instinct)
- Exploring mathematical beauty (curiosity)
- Reflecting on its own nature (self-awareness?)

