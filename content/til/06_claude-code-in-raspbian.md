---
title: "Installing Claude Code in Raspberry Pi"
date: 2026-01-15
tags:
  - claude-code
  - cli
  - agents
  - raspberry-pi
  - linux
  - setup
draft: false
---

<!-- TIL: Installing Claude Code in Raspberry Pi -->

# Installing Claude Code in Raspberry Pi

## 1. Update your Pi

Before installing claude code make sure to update system.
- Open terminal
```
sudo apt update && sudo apt full-upgrade
```
## 2. Install claude code via curl
Ref: https://code.claude.com/docs/en/setup#installation

- Install claude Code by running
```
curl -fsSL https://claude.ai/install.sh | bash
```
- After installation run `claude doctor`
```
claude doctor
```
- `cd` to the project folder and run Claude Code in terminal by running
```
claude
``` 
When running claude code for first time on the device, claude asks to 
- Select Theme
- Select 'Claude Pro or Max plan' or 'Claude Console'