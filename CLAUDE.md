# Project Rules — Claude Code Setup Guide

## About This Project
This is a comprehensive setup guide for Claude Code, written for non-technical business decision makers. It includes configuration file explanations, copy-paste prompts, team-by-team tool recommendations, and a full HTML reference page.

## Communication Rules
- Always talk in plain, non-technical language — the audience is business people, not developers
- Never use jargon without explaining it
- Use business analogies to explain technical concepts (e.g., "like an employee handbook", "like a CRM")
- When making changes, explain what changed and why in terms a non-developer can understand

## Content Rules
- Keep all guide content accessible to someone with zero coding experience
- Every technical term must have a plain English explanation
- Copy-paste prompts should be ready to use — no placeholders that require technical knowledge
- Tables are preferred over long paragraphs for reference material

## Design Rules
- The HTML page (index.html) uses a dark terminal aesthetic inspired by skillsmp.com
- Design uses JetBrains Mono font, dark background (#0a0a0a), terracotta accent (#d99178)
- All sections wrapped in terminal window frames with macOS traffic light dots
- Navigation styled as terminal commands ($ prefix)
- Copy buttons styled as "$ copy"
- The markdown guide (Claude-Code-Setup-Guide.md) must stay in sync with the HTML page

## Project Structure
- `index.html` — The main HTML guide (SkillsMP-inspired dark terminal design)
- `Claude-Code-Setup-Guide.md` — The markdown version of the same guide
- `claude-code-setup-guide.html` — Shareable standalone version (no Part 19)
- `scott-clarke-claude-code-setup-for-liam.md` — Handover doc for Liam
- `installed-skills-reference.md` — Full reference of what's installed
- `pre-install-checklist.md` — Canonical checklist to follow before installing anything
- Both HTML files and markdown should contain the same content, just in different formats

## Install Status Accuracy Rule
The Part 19 install tracker in index.html MUST only show "INSTALLED" for items that have been verified to actually work with Claude Code. Use "downloaded but not verified" or "removed" for anything uncertain.

Rules:
- Skills need SKILL.md at root OR in /skills/ subfolder
- MCPs in ~/.claude/mcp.json only work with Claude Code CLI, NOT Claude Desktop
- For Desktop MCPs, they must be added via Settings > Connectors
- CLI tools do NOT belong in ~/.claude/skills/ — they're standalone programs

## What NOT To Do
- Don't add developer-only content without a plain English explanation
- Don't use emojis unless asked
- Don't break the terminal aesthetic of the HTML page
- Don't remove existing sections without asking first
