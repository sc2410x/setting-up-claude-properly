# Scott Clarke — Claude Code Setup Overview
**For Liam (Technical Director) — April 2026**

Hi Liam, this is a full breakdown of how I've set up Claude Code, what global rules are in place, and the processes we've established. Sharing this so you've got visibility on the full picture.

---

## How Claude Code Is Set Up

### Global Configuration
I have a global `~/.claude/CLAUDE.md` file that applies to every project I open in Claude Code. This means I don't need to repeat instructions — they carry over automatically.

### Per-Project Configuration
Each project also has its own:
- **CLAUDE.md** — project-specific rules (on top of the global ones)
- **Context.md** — background about the project, audience, goals, decisions
- **Memory folder** — Claude remembers preferences, project status, and where we left off

### Installed Globally (All Projects)
Two repos installed at `~/.claude/skills/` that work across every project:

| Repo | What It Does |
|------|-------------|
| **Superpowers** (obra) | Planning, brainstorming, TDD, systematic debugging, code review, verification, git worktrees, subagent-driven development |
| **Everything Claude Code** (affaan-m) | Pre-built agents, AgentShield security scanner, memory/token optimisation, hooks, workflow rules |

### All Installed Skills
These are available globally in `~/.claude/skills/`:

| Skill | Purpose |
|-------|---------|
| audit-website | SEO, performance, security, and technical audits |
| brainstorming | Explore ideas before building |
| content-strategy | Content planning and topic clusters |
| copywriting | Marketing copy for pages |
| dispatching-parallel-agents | Run independent tasks in parallel |
| everything-claude-code | Power-user starter pack |
| executing-plans | Execute implementation plans with review checkpoints |
| find-skills | Discover and install new skills |
| finishing-a-development-branch | Guide merge, PR, or cleanup when work is done |
| football-betting-props | Football match betting analysis |
| marketing-psychology | Behavioural science applied to marketing |
| nba-betting-props | NBA player prop analysis |
| paid-ads | PPC campaign management across platforms |
| programmatic-seo | SEO-driven pages at scale |
| receiving-code-review | Handle incoming code review feedback |
| requesting-code-review | Request code review before merging |
| seo-audit | Technical SEO diagnostics |
| social-content | Social media content creation |
| startup-business-analyst-business-case | Investor-ready business case documents |
| startup-strategy-council | 6-advisor strategy council |
| subagent-driven-development | Two-stage review with sub-agents |
| superpowers | Full development methodology |
| systematic-debugging | Methodical bug diagnosis |
| tdm-competitor-analysis | TDM competitor SEO auditing |
| test-driven-development | Tests first, implementation after |
| using-git-worktrees | Isolated workspaces for parallel work |
| using-superpowers | Skill discovery and usage |
| verification-before-completion | Verify before claiming "done" |
| video-editing | AI-assisted video editing workflows |
| writing-plans | Break specs into implementation plans |
| writing-skills | Create and edit skills |

---

## Global Rules (Apply to Every Project)

### Communication
- Always plain, non-technical language — I'm not a developer
- Explain what changed and why after every change
- Don't build anything without discussing first
- Ask questions before assuming
- Do as much as possible for me — walk me through anything I need to do
- Always British English spelling

### Technical
- Never ask for a Claude API key — always use my subscription
- Never ask me to run terminal commands — Claude runs them directly
- If my input is needed, explain in the simplest possible terms

### End of Session
Before wrapping up any piece of work, Claude asks: "Shall I update the project files before we finish?" If I say yes, it:
1. Updates CLAUDE.md with new rules, preferences, or decisions
2. Updates Context.md with new project context
3. Updates Memory with anything to remember for next time
4. Gives me a plain-language summary of what changed

---

## New Build / Project Process

Every new project follows three mandatory steps. Nothing gets built until all three are completed and approved.

### Step 1: Understand the Idea
After I share the idea:
- Claude writes it back in its own words to prove understanding
- Asks any clarifying questions
- Confirms if it's a TDM project (TDM standards apply if yes)
- Doesn't move forward until I confirm understanding is correct

### Step 2: Write the Spec
A specification document covering:
- What we're building and why
- Who it's for
- Features and functionality
- Design direction (TDM standards if applicable)
- Technical setup I need to know about (in plain language)
- What's out of scope
- I review and approve before Step 3

### Step 3: Create the Plan
A step-by-step implementation plan covering:
- Technical requirements (what to build, in what order)
- Project requirements (what I need to provide, decisions to make)
- Phases or milestones (stages I can review)
- Dependencies
- I review and approve before any building starts

---

## Writing Style Profile

When Claude writes as me (emails, messages, client comms), it follows my exact style:

- **Tone:** Friendly, confident, honest. Professional without being corporate.
- **East Midlands flavour:** "mate", "duck", "Oh aye?", "cheers"
- **Go-to phrases:** "Happy to jump on a call", "No worries", "Give me a shout", "No pressure at all"
- **Never says:** "reach out", "touch base", "circle back", "leverage", "synergise", "awesome", "amazing", "fantastic"
- **Problems:** Fully transparent, take ownership, outline what's being done. Never minimise.
- **Sign-offs:** "Kind Regards" (formal), "Cheers" (casual)

---

## TDM Internal App Standards

When a project is confirmed as a TDM build, Claude automatically follows our full internal app standards:

### Stack
| Layer | Choice |
|-------|--------|
| Runtime | Bun |
| Framework | Next.js App Router |
| Language | TypeScript strict mode |
| Styling | Tailwind v4 + shadcn/ui |
| ORM | Drizzle |
| Database | Neon serverless PostgreSQL |
| Hosting | Vercel |
| Charts | Recharts via shadcn Charts |
| Tests | Vitest (unit) + Playwright (E2E) |
| Icons | Lucide |

### Theme
- Primary: TDM purple `#5B1AB2`
- CTA buttons: TDM pink `#F472B6`, hover `#EC4899` (solid, never gradient)
- Font: Satoshi from fontshare
- Cards: borderless, `rounded-2xl bg-white shadow-sm`
- Light mode only
- Nav: dark purple `bg-[#1F004B]`, app name with pink dot, hamburger on mobile

### Conventions
- GitHub repos: `internal-tdm-{appname}` in `thedigitalmaze` org
- Neon databases: `tdm-{appname}`
- CI/CD: GitHub Actions (lint, test, build) then Vercel auto-deploys on merge
- Block crawlers on all internal apps
- Ship `.env.example`, never commit `.env.local`
- TypeScript strict, no `any`, Drizzle for all queries, British English

### What We Don't Use
npm/yarn, Prisma, CSS modules, component libraries (MUI, Chakra), Pages Router, dark mode, gradients on buttons, emdashes in copy

---

## Reference Guide (Published)

I also built a full setup guide that covers everything from config files to team-specific tool recommendations:

- **Live site:** https://setting-up-claude-properly.vercel.app
- **GitHub:** https://github.com/sc2410x/setting-up-claude-properly
- **Shareable HTML:** `claude-code-setup-guide.html` (standalone file, no server needed)

The guide has 19 sections including repos/skills/MCPs with install commands, copy-paste prompts, agents and agent teams, tools by team, and resources/people to follow.

---

Give me a shout if you've got any questions or want to tweak anything, mate.

Cheers,
Scott
