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

## Key Terminology Clarification (added April 2026)
- **MCP** = Model Context Protocol (the standard)
- **MCP Server** = The actual connector to a specific service (technical name)
- **Connector** = What Claude Desktop UI calls MCP servers (user-facing name)
- All three refer to the same thing — different layers of naming

## Who Can Install What (added April 2026)
**Claude can do directly:**
- Clone repos and skills (just downloading files)
- Edit config files like CLAUDE.md, Context.md, mcp.json (just editing text)

**User must do themselves:**
- Add Claude Desktop Connectors (Settings > Connectors > Add custom connector)
- Sign in to each service (OAuth flows happen in browser)
- Approve access to external accounts (Semrush, Otter, GitHub, etc.)

This is by design — Anthropic prevents AI from granting itself access to external services.

## Free vs Paid MCPs (added April 2026)
For Google marketing stack (GA4, GSC, Google Ads, GTM):
- All Desktop-compatible options have free tiers but with usage limits
- Truly free forever options require Claude Code CLI (not Desktop)
- Current recommendation: skip Google marketing MCPs; use Semrush/Ahrefs subscriptions already in place
- When needed, install Claude Code CLI + free official Google MCPs

## Connectors Added In This Session (April 2026)
**Via Claude Desktop custom connector (Smithery hosted):**
- Trello — connected and tested, working in Claude Code sessions
- Default routing: Tasks board (id: 5d8248dbc8400359e9059063)

**MCP config cleaned up:**
- `~/.claude/mcp.json` emptied (had 7 entries for CLI that I don't use)

## Scott's Role and Accounts
- **Role:** Operations Director at The Digital Maze (TDM), 20-25 person UK digital agency
- **TDM accounts:** GitHub (thedigitalmaze org), Vercel (TDM team), Supabase (TDM), Neon (TDM)
- **Personal accounts:** GitHub (sc2410x), Vercel (scott-clarkes-projects-a84ccb32), Supabase (personal, pending), Neon (personal, pending)
- **Lootloop migration:** Moving from TDM accounts to personal, scheduled for separate session

## Key Project Artefacts
- `index.html` — Main guide with SkillsMP-style design
- `Claude-Code-Setup-Guide.md` — Markdown version
- `claude-code-setup-guide.html` — Shareable version (Part 19 removed)
- `scott-clarke-claude-code-setup-for-liam.md` — Handover for Liam (Technical Director)
- `installed-skills-reference.md` — Full skill inventory
- `pre-install-checklist.md` — Canonical pre-install rules
- `mcp-install-instructions.md` — MCP/Connector URL reference

## Rob's Work (For Inspiration)
Rob Twells at TDM has built:
- **Claude Vault** — personal dashboard for managing Claude skills, prompts, projects, sessions, usage analytics
- **Pulse** — internal ops dashboard with KPI scorecard, deliverables, initiatives, CEO review, weekly submissions, roadmap
- Both could inform a similar internal tool for Scott as Ops Director

## Session Additions (late April 2026)

### Session Wrap-Up Artefacts
- `tdm-onboarding.md` — New starter guide for TDM team members
- `decisions.md` — Decision log with 4 captured decisions
- Backup: `github.com/sc2410x/claude-global-backup` (private)
- 6 macOS Text Replacement shortcuts set up (`;;setup`, `;;check`, `;;catchup`, `;;wrap`, `;;explain`, `;;endofday`)

### Key Realisations This Session
- **Slash commands don't work reliably in Claude Desktop** — despite multiple attempts to register them via `~/.claude/commands/` and skill packages. Fell back to macOS Text Replacement which works everywhere.
- **Custom connectors = Desktop connectors** when added via Settings > Customize > Connectors. The URL source (Smithery, Composio, etc.) doesn't change that.
- **Agent verification is critical** — claiming things are installed based on cloning/file creation repeatedly caused problems. Must verify Claude actually uses a feature before marking INSTALLED.
- **AgentShield F grade is mostly noise** — third-party skills installed (alirezarezvani, everything-claude-code) flag as risky, but Scott's own config is clean.

### Tools Decision
- **Staying with Claude Desktop only** — no Claude Code CLI install. Scope of work doesn't need it.
- **Free Google marketing MCPs deferred** — can revisit if SEO team needs them; using Semrush + Ahrefs for now.
- **1Password CLI deferred** — will revisit when building TDM apps with real secrets.
- **GSC MCP (Suganthan's)** considered but parked — Semrush/Ahrefs cover the gap for now.

## Scott's Business Structure
Scott runs a digital agency with 12 teams: SEO, PPC, Web Dev, Web Design, Client Services, Project Management, Finance, Operations Director, Managing Director, Technical Director, Internal Brand Marketing, Sales.
