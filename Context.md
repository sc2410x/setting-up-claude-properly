# Project Context — Claude Code Setup Guide

## What This Project Is
A comprehensive reference guide that helps non-technical business people set up and get the most out of Claude Code. It started as a simple "explain these config files" request and grew into a 20-section guide covering everything from first setup to team-specific tool recommendations.

## Who It's For
- Scott Clarke (the creator) — a business decision maker, not a developer
- His teams — SEO, PPC, Web Dev, Web Design, Client Services, Project Management, Finance, Operations Director, Managing Director, Technical Director, Internal Brand Marketing, Sales
- Anyone else who wants to set up Claude Code without technical knowledge

## What's Been Built
1. **Claude-Code-Setup-Guide.md** — A full markdown guide (20 parts)
2. **index.html** — A polished HTML version with dark terminal design inspired by skillsmp.com

## The 20 Sections
1. The 4 Setup Files (CLAUDE.md, Context.md, Memory, Skills)
2. Add-Ons to Install (Repos with install commands)
3. Skills to Install
4. Where Everything Lives (folder map)
5. Jargon Buster (glossary)
6. Where to Find More Stuff (marketplaces, directories)
7. Copy-Paste Prompts (8 ready-to-use prompts including the recommended first message)
8. How to Talk to Claude Effectively
9. Common Mistakes and What to Avoid
10. What to Do When Claude Gets Stuck
11. How to Review Claude's Work (When You're Not Technical)
12. Security Basics
13. Cost and Usage Awareness
14. Claude Code vs Regular Claude Chat
15. How to Structure Projects
16. Backup Basics (Version Control)
17. Troubleshooting FAQ
18. Recommended Tools by Team (12 teams with specific skills, MCP servers)
19. Resources, People to Follow, YouTube Channels, Newsletters
20. Installation Status Tracker

## Key Decisions Made
- The guide is written entirely in plain, non-technical language
- Business analogies are used throughout (employee handbook, CRM, consultant briefing, etc.)
- The HTML design replicates the skillsmp.com terminal/code-editor aesthetic
- Superpowers repo has been installed globally at ~/.claude/skills/superpowers
- The "Recommended First Message" prompt was identified as the single most important prompt

## Deployment
- **GitHub repo:** https://github.com/sc2410x/setting-up-claude-properly
- **Live site:** https://setting-up-claude-properly.vercel.app
- Vercel is connected to GitHub — pushing to main auto-deploys

## What's Installed So Far (Verified April 2026)
**Working as Claude Code skills (verified):**
- Superpowers (14 skills)
- UI UX Pro Max (6 skills extracted to top-level)
- Marketingskills by Corey Haines (36 skills)
- Product Manager Skills (47 skills, including Jobs to Be Done)
- Alirezarezvani Skills (301 skills via symlink fix)
- Claude Office Skills (4 skills via symlink fix)
- claude-seo (19 skills)
- claude-ads (20 skills)
- Browser Use (4 skills)
- Web Asset Generator (1 skill)
- Everything Claude Code (183 skills)
- 20+ standalone individual skills (copywriting, seo-audit, etc.)

**MCPs added to ~/.claude/mcp.json (Claude Code CLI only, NOT Desktop):**
- GitHub, Google Search Console, Google Analytics 4, Ahrefs, Semrush, Cross-Platform Ads, Google Workspace
- These DON'T work in Claude Desktop app — Desktop needs them added via Settings > Connectors

**Removed because incompatible:**
- deep-research (no SKILL.md files)
- claude-mem (CLI tool, not a skill)
- trailofbits-security (plugin format, not a skill — but files still on disk)

## Lessons Learned
- "Cloned successfully" ≠ "Installed and working"
- A repo's structure determines if it works as a skill
- Claude Desktop and Claude Code CLI use different MCP systems
- CLI tools should not be installed to ~/.claude/skills/
- Always verify before claiming installed (see pre-install-checklist.md)

## Scott's Business Structure
Scott runs a digital agency with 12 teams: SEO, PPC, Web Dev, Web Design, Client Services, Project Management, Finance, Operations Director, Managing Director, Technical Director, Internal Brand Marketing, Sales.
