---
title: "Installing Gemini CLI & Codex CLI in Raspberry Pi"
date: 2026-01-18
tags:
  - codex
  - gemini
  - cli
  - agents
  - raspberry-pi
  - linux
  - setup
draft: false
---

<!-- Installing Gemini CLI & Codex CLi in Raspberry Pi -->

## 1. Update your Pi

Before installing claude code make sure to update system.
- Open terminal
```
sudo apt update && sudo apt full-upgrade
```

> [!TIP]
> Gemini and Codex needs npm to be installed. so check if node and npm are installed

## 2. Check if node and npm are installed 
```
node --version
npm -version
```
***If node and npm are not installed then install by running***
```
sudo apt-get install -y nodejs npm
```

## To Install Gemini CLI
Ref: https://geminicli.com/docs/get-started/

- Install Gemini CLI by running
```
sudo npm install -g @google/gemini-cli
```
- Run `gemini` and authenticate

## To Install Codex CLI
Ref: https://developers.openai.com/codex/cli/

- Install Codex CLI by running
```
sudo npm i -g @openai/codex
```
- Run `codex` and authenticate
- Upgrade to latest version of codex by running
```
sudo npm i -g @openai/codex@latest
```