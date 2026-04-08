# Claude Code Project Setup Guide
**Created: 7 April 2026**

This guide explains how to set up Claude Code so it works smarter on your projects. It's written for non-technical people — no coding experience needed.

**What is Claude Code?** It's an AI assistant that lives in your computer's command line (Terminal on Mac). Unlike regular ChatGPT-style chat, Claude Code can read your files, edit your code, run commands, and build things for you. But it works best when you tell it about your project first — that's what this guide helps you do.

---

## Part 1: The 4 Setup Files (What They Are and Why They Matter)

When you start a new project with Claude Code, there are 4 things you can set up to make it work better. None of them are compulsory, but the more you set up, the smarter Claude behaves.

| File | What It Does | Think of It Like... |
|------|-------------|---------------------|
| **CLAUDE.md** | Your "house rules" — tells Claude how to behave in this project | An employee handbook you give a new hire on day one |
| **Context.md** | Background about your business, goals, and audience | A briefing document you'd give a consultant before they start advising you |
| **Memory** | Lets Claude remember things about you across conversations | A CRM that tracks your relationship history so you don't repeat yourself |
| **Skills** | Pre-written step-by-step guides that make Claude better at specific tasks | Standard Operating Procedures (SOPs) — proven playbooks your team follows |

### CLAUDE.md (sometimes called AGENTS.md)

This is the most important file. It's a simple text file you put in your project folder that tells Claude the rules for this project.

- **Where it goes:** In the main folder of your project (e.g., `~/Sites/my-project/CLAUDE.md`)
- **What to write in it:** Your preferences, do's and don'ts, what the project is about, what tools or services you use
- **Example of what it might say:**
  > "This is a marketing website for [company]. Always write in a friendly, professional tone. Never delete existing content without asking first. I'm not a developer — always explain things in plain language."

### Context.md

This gives Claude the "big picture" so it understands *why* you're doing things, not just *what* you're doing.

- **Where it goes:** In the main folder of your project, next to CLAUDE.md
- **What to write in it:** What your business does, who your customers are, what stage the project is at, key decisions you've already made and why

### Memory

This is Claude's "notebook." Without it, every time you start a new conversation, Claude starts from scratch with no idea who you are. With memory, it remembers things like your preferences, your role, and where you left off.

- **Where it lives:** Claude manages this automatically in a hidden folder on your computer
- **How to use it:** Just tell Claude "remember that I prefer X" during any conversation and it saves it. It builds up naturally over time — you don't need to manage the files yourself.

### Skills

Skills are like instruction manuals that make Claude an expert at specific tasks. Without them, Claude figures things out from scratch each time. With them, it follows a proven process.

- **Where they live:** In a folder called `~/.claude/skills/` on your computer (the `~` just means your home folder)
- **How to use them:** You install them once (see Part 2 below) and they work automatically across all your projects

---

## Part 2: Add-Ons to Install (Repos)

A "repo" (short for repository) is just a folder of files stored on GitHub — think of GitHub as a public library for software. "Installing a repo" simply means downloading that folder to the right place on your computer.

### How to Install Any Repo

Open the **Terminal** app on your Mac (search for "Terminal" in Spotlight) and paste this command:

```
git clone <github-url> ~/.claude/skills/<name>
```

Replace `<github-url>` with the web address of the repo, and `<name>` with a short name for it.

**You only need to do this once per repo** — it then works across every project on your computer.

---

### What Each Repo Does and How to Install It

| Repo | What It Does (In Plain English) | Install Command |
|------|-------------------------------|-----------------|
| **Superpowers** | Makes Claude much better at planning work, brainstorming ideas, reviewing quality, and working through tasks methodically — like upgrading from a junior assistant to a senior team member | `git clone https://github.com/obra/superpowers.git ~/.claude/skills/superpowers` |
| **Everything Claude Code** | A pre-built starter kit with recommended settings, useful skills, and workflows already organised — saves you hours of setup | `git clone https://github.com/anthropics/everything-claude-code.git ~/.claude/skills/everything-claude-code` |
| **UI UX Pro Max** | Makes Claude great at designing professional-looking websites and apps — good layouts, proper spacing, modern design | `git clone https://github.com/nicholasoxford/ui-ux-pro-max.git ~/.claude/skills/ui-ux-pro-max` |
| **Browser Use** | Lets Claude actually open and use a web browser — navigate websites, click buttons, fill in forms, and take screenshots | `git clone https://github.com/browser-use/browser-use.git ~/.claude/skills/browser-use` |
| **claude-mem** | An upgraded memory system that helps Claude remember more detail across longer, more complex projects | `git clone https://github.com/sdairs/claude-mem.git ~/.claude/skills/claude-mem` |
| **n8n-mcp** | Connects Claude to n8n, a popular automation platform (similar to Zapier but more powerful) — lets Claude trigger automated workflows across your business tools | `git clone https://github.com/n8n-io/n8n-mcp.git ~/.claude/skills/n8n-mcp` |

> **Heads up:** GitHub repos can sometimes move or get renamed. If a command fails with an error, search GitHub.com for the repo name to find the current web address.

---

## Part 3: Skills to Install

These are specialised playbooks that make Claude better at specific tasks. Think of each one as hiring a specialist consultant for that particular area.

| Skill | What It Does (In Plain English) | When You'd Use It |
|-------|-------------------------------|-------------------|
| **Marketing Skills Library** (by Corey Haines) | Turns Claude into a full marketing team — copywriting, content strategy, SEO, paid ads, social media, and more. Each skill follows proven marketing frameworks. | Any time you need marketing help |
| **Web Assets Generator** | Creates the images you need for websites and social media — banners, icons, social sharing images — properly sized and formatted | When you need visuals for your website or social accounts |
| **Jobs to Be Done** | Uses the "Jobs to Be Done" framework (a respected business strategy method) to help you understand what your customers actually want and why they buy | Product decisions, positioning, figuring out your market |
| **Explain Code** (Official, by Anthropic) | Translates code into plain English so you can understand what's happening without being technical | Any time you see code and want to know what it does |
| **Deep Research** | Makes Claude do thorough, multi-step research — checking multiple sources, cross-referencing facts, and delivering detailed findings with sources cited | Market research, competitor analysis, due diligence, big decisions |

---

## Part 4: Where Everything Lives on Your Computer

Here's a simple map of where all these files and folders sit. The `~` symbol is just a shortcut that means your home folder (on a Mac, that's `/Users/[yourname]/`).

**Claude's global settings and skills** (shared across all projects):
```
~/.claude/
  ├── skills/                          <-- All your installed add-ons live here
  │   ├── superpowers/                 <-- Example: the Superpowers add-on
  │   ├── ui-ux-pro-max/              <-- Example: the UI UX Pro Max add-on
  │   └── ...                          <-- Any others you install
  │
  └── projects/
      └── [project-name]/
          └── memory/                  <-- Claude's memory for each specific project
              ├── MEMORY.md            <-- An index of everything Claude remembers
              └── [memory files...]    <-- Individual things Claude has remembered
```

**Your individual project folder** (one per project):
```
~/Sites/my-project/                    <-- Your project folder
  ├── CLAUDE.md                        <-- House rules for THIS project
  ├── Context.md                       <-- Background info for THIS project
  └── [your project files...]          <-- Everything else in your project
```

---

## Part 5: Glossary (Jargon Buster)

If you come across any of these terms elsewhere, here's what they mean:

| Term | What It Actually Means |
|------|----------------------|
| **Repo** (Repository) | A folder of files stored on GitHub — like a shared Google Drive folder, but for code |
| **git clone** | A command that downloads a repo from GitHub to your computer |
| **Terminal** | The app on your Mac where you type commands. Find it by searching "Terminal" in Spotlight (Cmd + Space) |
| **`~`** (tilde) | A shortcut that means "my home folder." On your Mac, that's `/Users/[yourname]/` |
| **MCP** (Model Context Protocol) | A way to plug Claude into other apps and services (like Slack, Google Drive, databases, etc.) — think of it as an adapter or bridge |
| **Slash command** | Typing `/` followed by a word to trigger a specific skill. For example, typing `/commit` tells Claude to save your work to version control |
| **Global** | Something that works across all your projects, not just one specific project |
| **Root folder** | The main, top-level folder of your project — not a subfolder inside it |
| **Plugin** | An add-on that gives Claude new abilities — similar to browser extensions that add features to Chrome |
| **Hook** | An automatic action that runs when something specific happens — like an "if this, then that" rule for Claude |

---

## Part 6: Where to Find More Add-Ons, Skills, and Tools

There's a big ecosystem of free tools, skills, and add-ons you can browse and install. Here are the best places to look.

### Start Here (The Top 5)

| What You're Looking For | Where to Go | What You'll Find |
|------------------------|-------------|-----------------|
| **Official, trusted plugins** | claude.com/plugins | Anthropic's own store — look for the "Verified" badge for extra trust |
| **MCP servers** (adapters that connect Claude to other apps) | registry.modelcontextprotocol.io | The official directory, backed by Anthropic, GitHub, and Microsoft |
| **The biggest collection of MCP servers** | mcp.so | Over 19,500 adapters — searchable by what they connect to |
| **The biggest skills library** | skillsmp.com | Over 700,000 pre-built skills you can install |
| **One massive curated list of everything** | github.com/rohitg00/awesome-claude-code-toolkit | 135 agents, 400K+ skills, 150+ plugins — all organised in one place. This is the best single bookmark. |

### More Places to Find MCP Servers (App Connectors)

MCP servers are "adapters" that plug Claude into other apps you already use — like Slack, Google Drive, Notion, your database, etc.

| Website | What's There |
|---------|-------------|
| mcp.so | 19,500+ servers — the largest directory |
| glama.ai/mcp/servers | Updated daily. Can also host and run servers for you |
| pulsemcp.com/servers | 11,000+ servers |
| smithery.ai | The original MCP marketplace — well established |
| composio.dev/toolkits | 500+ ready-made app connections (Slack, Notion, Google, etc.) |
| mcpmarket.com | Organised by category — easy to browse |
| mcpservers.org | A curated "best of" MCP servers list |
| lobehub.com/mcp | Another large marketplace |

### More Places to Find Skills (Task Playbooks)

| Website | What's There |
|---------|-------------|
| skillsmp.com | 700,000+ skills — the largest library |
| skillhub.club | Focused on Claude-specific skills |
| lobehub.com/skills | Thousands of skills, easy to filter by category |
| mcpmarket.com/tools/skills | The skills section of MCP Market |

### Curated "Best Of" Lists on GitHub

These are community-maintained collections where people gather and organise the best tools in one place — like a "recommended reading" list:

| List | What Makes It Worth Bookmarking |
|------|-------------------------------|
| github.com/rohitg00/awesome-claude-code-toolkit | The most complete — covers everything in one place |
| github.com/hesreallyhim/awesome-claude-code | Great for skills, shortcuts, and automation ideas |
| github.com/travisvn/awesome-claude-skills | Focused specifically on skills |
| awesomeclaude.ai | A visual, browsable website (easier than reading GitHub) |

### Plugin Directories

Plugins are add-ons that give Claude new abilities (like browser extensions add features to Chrome):

| Website | What's There |
|---------|-------------|
| claude.com/plugins | The official Anthropic directory — most trusted |
| claudemarketplaces.com | Pulls together plugins from multiple sources |
| claudepluginhub.com | Community-run plugin directory |
| claudex.directory | Browse and install Claude extensions |

### Communities (Where People Share Tips and Setups)

| Where | What Happens There |
|-------|--------------------|
| reddit.com/r/ClaudeCode | The main community — people share setups, ask questions, and troubleshoot problems |
| reddit.com/r/ClaudeAI | The broader Claude community (not just Claude Code) |
| github.com/ykdojo/claude-code-tips | 45+ practical tips, from basics to advanced |
| claudelog.com | Guides, tutorials, and best practices |

---

## Part 7: Copy-Paste Prompts (Your Cheat Sheet)

These are ready-to-use messages you can paste straight into Claude Code. Think of them as "magic phrases" — just copy, paste, and Claude will do the rest.

**How to use them:** Open Claude Code in any project, paste the text from the grey box, and press Enter.

---

### "Is This Project Set Up Properly?" (Health Check)

**When to use it:** When you open any project and want to check if the setup files are in place.

```
Check if this project has the following configuration files set up properly. For each one, tell me: does it exist, where is it, and is it empty or does it have content? Give me a simple status report.

1. CLAUDE.md (or AGENTS.md) — the "house rules" file in the project root
2. Context.md — background info file in the project root
3. Memory system — look for ~/.claude/projects/ folder that matches this project, and check for MEMORY.md inside it
4. Skills — check if ~/.claude/skills/ exists and what's installed there

For anything that's missing or empty, tell me what it should contain in plain, non-technical language. I'm not a developer — I'm a business decision maker.

Format your answer as a simple table:
| File | Status | What to Do |
```

---

### The Recommended First Message for Any New Project

**When to use it:** This is the very first thing you should paste into Claude Code after creating a new project folder. It sets the tone, establishes your working relationship, and gets everything configured properly through conversation.

```
Hi Claude. I've just created this project folder and I need your help setting it up properly and building it out.

Before we do anything, here's what you need to know about me:
- I'm a business decision maker, not a developer
- Always talk to me in plain, non-technical language
- When you make changes, explain what you did and why in terms I can understand
- Don't build anything until we've talked through what I need first
- Ask me questions before making assumptions

Let's start by getting this project set up:

1. Ask me about the project — what it is, who it's for, what I want it to achieve, and any preferences I have. Use these answers to create the CLAUDE.md and Context.md files.

2. Set up your memory system for this project so you remember our conversations.

3. Check that global skills (like Superpowers) are installed and available.

4. Once setup is done, give me a status report and then ask me what I'd like to work on first.

Let's go.
```

**Why this works so well:**
- Sets boundaries immediately — Claude knows you're not technical before it says a single word
- Establishes the working relationship — it asks questions first instead of guessing
- Gets the config files created through conversation, not you writing them manually
- Ends with a handoff — Claude asks you what's next, keeping you in the driver's seat

---

### "Get Up to Speed" (Starting a Session)

**When to use it:** At the start of a new conversation, so Claude quickly catches up on where you left off.

```
Read the CLAUDE.md, Context.md, and your memory for this project. Then give me a brief summary of:
1. What this project is
2. Where we left off
3. What's pending or next

Keep it to a few sentences. I'll tell you what I want to work on today.
```

---

### "Update Everything Before We Finish" (End of Session)

**When to use it:** When you're about to finish a work session and want Claude to save everything important before you close out.

```
Before we wrap up, please do the following:

1. Update CLAUDE.md — Add any new rules, preferences, or decisions we made during this session that should apply going forward. Don't remove existing content, just add what's new.

2. Update Context.md — Add any new context about the project, business, audience, or strategy that came up during this session.

3. Update Memory — Save anything important about me, my preferences, or project status that you should remember for next time.

4. Give me a short summary of what was added to each file so I know what changed.

Talk to me in plain language — I'm not a developer.
```

---

### "Full Project Debrief" (End of Day)

**When to use it:** At the end of a full day of work, when you want a thorough wrap-up and update of everything.

```
End of day debrief. Please do the following:

1. Review everything we worked on today and summarise the key decisions, changes, and progress made.

2. Update CLAUDE.md with any new project rules or preferences discovered today.

3. Update Context.md with any new business context, goals, or strategic decisions from today.

4. Update Memory with anything you should remember about me, the project, or our working style for future sessions.

5. Create a brief "session log" summary I can refer back to — what we did, what's done, and what's still pending.

Keep everything in plain language. I'm a business decision maker, not a developer.
```

---

### "Remember This" (Save Something Specific)

**When to use it:** Any time during a conversation when you want Claude to remember a specific fact or preference for the future.

Just type:
```
Remember this for all future sessions: [write what you want remembered here]
```

**Examples:**
- "Remember this for all future sessions: I prefer British English spelling."
- "Remember this for all future sessions: Our target audience is small business owners aged 30-50."
- "Remember this for all future sessions: We use Stripe for payments and Vercel for hosting."

---

### "Explain What Just Happened" (When You're Lost)

**When to use it:** When Claude did something and you're not sure what it was or why.

```
Explain what you just did in plain, non-technical language. I'm not a developer. Tell me:
1. What changed?
2. Why did you do it?
3. What does it mean for the project?
4. Is there anything I need to decide or approve?
```

---

### "Weekly Status Report" (Weekly Review)

**When to use it:** Once a week, to get a clear picture of where the project stands.

```
Give me a weekly project status report in plain language:

1. What has been built or changed this week?
2. What's working well?
3. What still needs to be done?
4. Are there any decisions I need to make?
5. Update the Context.md and CLAUDE.md if anything is outdated.

Format it like a business report, not a technical changelog. I'm a decision maker, not a developer.
```

---

## Part 8: How to Talk to Claude Effectively

Claude Code is powerful, but the quality of what it does depends heavily on how you ask. Here are the key principles.

### Be Specific, Not Vague

The more detail you give, the better the result. Think of it like briefing a freelancer — "make it better" gets you guesswork; a clear brief gets you what you want.

| Instead of this... | Say this... |
|--------------------|------------|
| "Fix the website" | "The contact form on the homepage isn't sending emails. Can you find out why and fix it?" |
| "Write some copy" | "Write a homepage headline and subheadline for [company]. Our target audience is small business owners. The tone should be friendly and confident, not corporate." |
| "Make it look better" | "The pricing page feels cluttered. Can you simplify the layout, add more white space, and make the 'Pro' plan stand out as the recommended option?" |
| "Add a feature" | "Add a newsletter signup form to the footer of every page. It should collect first name and email, and connect to our Mailchimp account." |

### Tell Claude Your Role

Claude adjusts its communication style based on who it's talking to. If you don't tell it, it defaults to talking like you're a developer.

**Add this to your CLAUDE.md or say it at the start of a session:**
> "I'm a business owner, not a developer. Always explain things in plain language. When you make changes, tell me what changed and why in terms I can understand."

### Break Big Tasks Into Steps

If you need something complex, don't dump the entire thing in one message. Break it into stages:

1. **First:** "Let's plan what we need to build. Ask me questions before you start."
2. **Then:** "Now build the first part — just the homepage layout."
3. **Then:** "Now add the content to the homepage."
4. **Finally:** "Review everything and make sure it looks right."

This gives you checkpoints to review and course-correct, rather than getting something massive that's wrong.

### Give Examples

If you have a reference for what you want, share it:
- "Make it look similar to [website you like]"
- "The tone should be like [brand you admire]"
- "Here's an example of what I mean: [paste example text]"

### Say What You DON'T Want

Claude can't read your mind. If there are things you want to avoid, say so:
- "Don't use jargon or buzzwords"
- "Don't change any existing content — only add new sections"
- "Don't make it look like every other SaaS landing page"
- "Don't over-engineer this — keep it simple"

---

## Part 9: Common Mistakes and What to Avoid

These are the things that trip people up most often. Learn from others' mistakes.

### 1. Letting Claude Run Wild Without a Plan

**The mistake:** Asking Claude to "build me a website" and letting it go without reviewing along the way.

**What happens:** You end up with something that technically works but isn't what you wanted, and now it's harder to fix than if you'd guided it step by step.

**The fix:** Always start big tasks with planning. Say: "Before you build anything, let's talk through what I need. Ask me questions first." Use the Superpowers brainstorming skill for this.

### 2. Not Reviewing Before Approving

**The mistake:** When Claude asks "Can I edit this file?" or "Can I run this command?", clicking approve without reading what it's about to do.

**What happens:** Claude might delete something, overwrite your work, or make changes you didn't intend.

**The fix:** Read the description of what it wants to do. If you're unsure, ask: "Explain what this will do before I approve it." It's always better to slow down and ask than to approve something you don't understand.

### 3. Not Setting Up Config Files

**The mistake:** Jumping straight into work without creating CLAUDE.md or Context.md.

**What happens:** Claude makes assumptions about your project, your preferences, and your audience. You spend more time correcting it than you would have spent on setup.

**The fix:** Spend 10 minutes at the start of each project using the "Set Up This Project From Scratch" prompt from Part 7.

### 4. Asking for Too Much at Once

**The mistake:** "Build me a complete e-commerce website with user accounts, payments, inventory management, a blog, and an admin dashboard."

**What happens:** Claude tries to do everything, runs into limits, and the result is messy.

**The fix:** Break it into phases. Start with the most important thing. Get that right, then move on.

### 5. Forgetting to Update Config Files

**The mistake:** Working on a project for weeks but never updating CLAUDE.md or Context.md.

**What happens:** The files become outdated, and Claude starts making decisions based on old information.

**The fix:** Use the "End of Session" or "End of Day" prompts from Part 7 regularly.

### 6. Not Using Memory

**The mistake:** Repeating the same instructions every conversation — "I'm not a developer", "we use Stripe", "our audience is X".

**What happens:** Wasted time, and Claude might forget mid-project.

**The fix:** Tell Claude to remember important things: "Remember this for all future sessions: [your fact]"

---

## Part 10: What to Do When Claude Gets Stuck

Sometimes Claude goes in circles, repeats itself, or seems confused. Here's how to handle it.

### Signs Claude Is Stuck
- It keeps trying the same thing and failing
- It apologises repeatedly but doesn't fix the problem
- Its responses are getting longer but less useful
- It's suggesting increasingly complicated solutions for a simple problem

### How to Fix It

**Option 1: Restate the problem simply**
Stop and say:
```
Stop. Let's reset. Here's what I need in simple terms: [restate your goal in 1-2 sentences]. What's the simplest way to do this?
```

**Option 2: Break the problem down**
Say:
```
This isn't working. Let's break this into smaller pieces. What's the first thing we need to figure out?
```

**Option 3: Ask it to think differently**
Say:
```
You seem stuck on one approach. Can you think of a completely different way to solve this? What would a beginner try?
```

**Option 4: Start a new conversation**
Sometimes the best fix is to start fresh. Open a new Claude Code conversation — your CLAUDE.md, Context.md, and Memory will carry over, so you won't lose your project setup. Just explain the specific problem you were stuck on.

**Option 5: Ask for help**
Say:
```
I think we're stuck. Can you explain what's going wrong in plain language, and give me options for how to move forward? I'll decide which path to take.
```

---

## Part 11: How to Review Claude's Work (When You're Not Technical)

You don't need to understand code to be a good reviewer. Here's what to check.

### The "Does It Work?" Check

After Claude builds or changes something, ask:
```
Show me how to test what you just built. Walk me through it step by step.
```

Or if it's a website:
```
Open a preview of the site so I can see what it looks like.
```

### The "Did It Do What I Asked?" Check

Compare the result to your original request:
```
Compare what you just built against my original request. Did you miss anything? Did you add anything I didn't ask for?
```

### The "What Changed?" Check

If Claude edited existing files, ask:
```
Show me a summary of every file you changed and what you changed in each one. Keep it in plain language.
```

### The "Is It Safe?" Check

Before deploying anything or making it live, ask:
```
Before we go live with this, are there any security concerns? Did you accidentally include any passwords, API keys, or sensitive information in the code?
```

### The "Second Opinion" Check

For important changes, ask Claude to review its own work:
```
Now pretend you're a senior quality reviewer. Look at everything you just built with fresh eyes. What would you flag as a concern, and what would you improve?
```

### Trust But Verify

A good rule of thumb:
- **Trust Claude for:** Routine tasks, first drafts, research, organising information, generating ideas
- **Verify before approving:** Anything that goes live, anything involving money/payments, anything that deletes or overwrites existing work, anything security-related

---

## Part 12: Security Basics

Claude Code has access to your files and can run commands on your computer. That's what makes it powerful — but it also means you need to be smart about security.

### Things You Should NEVER Share With Claude (or Put in Your Project Files)

| Never share... | Why not |
|---------------|---------|
| **Passwords** | They'll end up stored in files on your computer or in conversation history |
| **API keys** (the secret codes that connect to services like Stripe, Mailchimp, etc.) | If these get into your code and uploaded anywhere, others could use your accounts and run up charges |
| **Credit card numbers or bank details** | Obvious reasons |
| **Personal data of your customers** (real names, emails, addresses) | Privacy regulations (GDPR, etc.) and basic ethics |
| **Private encryption keys or certificates** | These are the "master keys" to secure systems |

### Where to Keep Secrets Safely

Instead of putting sensitive information directly in your code, use a file called `.env` (short for "environment"). This is a special file that:
- Stores your secret codes and passwords
- Stays on your computer only
- Should NEVER be uploaded or shared

Ask Claude: "Help me set up a .env file for this project and show me how to keep it secure."

### What to Watch Out For

- **If Claude suggests committing or pushing a `.env` file** — say no. This file should stay private.
- **If Claude asks to install something unfamiliar** — ask "What does this do and is it from a trusted source?" before approving.
- **If you see passwords or API keys appearing in code** — tell Claude immediately: "There's a password/API key visible in the code. Remove it and put it in the .env file instead."

---

## Part 13: Cost and Usage Awareness

Claude Code uses credits or tokens every time you interact with it. Here's how to avoid wasting money.

### What Uses More Credits

| Uses MORE credits | Uses FEWER credits |
|-------------------|--------------------|
| Long, rambling requests | Short, specific requests |
| Asking Claude to read huge files unnecessarily | Pointing Claude to the specific file or section you need |
| Letting Claude over-engineer (build more than you asked for) | Telling Claude to keep it simple |
| Going back and forth 20 times because the brief was unclear | Giving a clear brief upfront |
| Asking Claude to rewrite the same thing over and over | Getting it right with a good first brief |

### Tips to Keep Costs Down

1. **Be specific upfront** — A clear first message saves 5 back-and-forth messages later
2. **Use the "planning" approach** — Planning before building is cheaper than rebuilding
3. **Say "keep it simple"** — Claude tends to over-build if you don't tell it otherwise
4. **Don't ask Claude to re-read files it's already read** — It remembers within a conversation
5. **Use the right tool for the job** — Don't use Claude Code for things regular Claude chat handles fine (see Part 14)

---

## Part 14: When to Use Claude Code vs Regular Claude Chat

They're different tools for different jobs. Using the wrong one wastes time and money.

### Use Claude Code When:

| Situation | Why Claude Code |
|-----------|----------------|
| Building or editing a website | It can directly create and modify files on your computer |
| Setting up a project | It can create folders, install packages, configure settings |
| Fixing a bug in your project | It can read your actual code, find the problem, and fix it |
| Running commands on your computer | It has access to your Terminal |
| Working with files (creating, editing, organising) | It can directly work with your file system |
| You need ongoing context across a project | CLAUDE.md, Context.md, and Memory keep it informed |

### Use Regular Claude Chat (claude.ai) When:

| Situation | Why regular chat |
|-----------|-----------------|
| Asking general questions | Faster, simpler, and doesn't need file access |
| Writing a one-off email or document | No need for project context |
| Brainstorming ideas (not tied to a project) | Quicker for general thinking |
| Having a conversation about strategy | Doesn't need access to your computer |
| Analysing a document or image (one-off) | Just upload it to claude.ai |
| Learning about a topic | Regular chat is simpler for pure knowledge questions |

### The Simple Rule

**If it involves files on your computer or an ongoing project** — use Claude Code.
**If it's a one-off question or task that doesn't need your files** — use regular Claude chat.

---

## Part 15: How to Structure Your Projects

A well-organised project folder helps both you AND Claude work more effectively.

### One Project = One Folder

Don't mix multiple projects in one folder. Each project should have its own folder:

```
~/Sites/
  ├── company-website/          <-- One project
  ├── marketing-landing-page/   <-- Another project
  ├── client-project-name/      <-- Another project
  └── personal-blog/            <-- Another project
```

### Every Project Should Have

At minimum, create these in each project folder:
- `CLAUDE.md` — House rules for this project
- `Context.md` — Background about this project

Use the "Set Up This Project From Scratch" prompt from Part 7 to create them.

### Naming Conventions

Use clear, descriptive folder names. Avoid spaces (use hyphens instead):

| Bad name | Good name |
|----------|-----------|
| `new folder` | `company-website` |
| `project2` | `client-smith-landing-page` |
| `stuff` | `marketing-assets` |
| `final final v2` | `product-launch-campaign` |

### Don't Put Everything in One Place

Keep different types of content separated:
```
my-project/
  ├── CLAUDE.md                 <-- House rules
  ├── Context.md                <-- Background
  ├── src/                      <-- Source code (the actual website/app)
  ├── assets/                   <-- Images, fonts, videos
  ├── docs/                     <-- Documentation and notes
  └── content/                  <-- Written content (blog posts, copy, etc.)
```

---

## Part 16: Backup Basics (Why Version Control Matters)

Version control (using a tool called "git") is like having an unlimited "undo" button for your entire project. Every time you save a version, you can always go back to it.

### Why It Matters (Even for Non-Developers)

- **You can undo anything.** If Claude (or you) makes a mistake, you can roll back to a previous version.
- **You can see what changed.** Every saved version has a note explaining what was different.
- **You won't lose work.** Even if files get accidentally deleted, they're saved in the version history.
- **You can try things safely.** Make experimental changes knowing you can always undo them.

### The Basics You Need to Know

You don't need to learn git in detail. Just know these three prompts to say to Claude:

**To save a snapshot of your current work:**
```
Save the current state of this project as a git commit. Describe what changed.
```

**To see what's changed since your last save:**
```
Show me what files have changed since the last commit, and summarise the changes in plain language.
```

**To undo recent changes and go back to a previous save:**
```
Show me the last 5 commits (saved versions) for this project, with a plain language description of each. I might want to go back to an earlier one.
```

### How Often to Save

- **After any significant piece of work** — finished a new page? Save it.
- **Before making big changes** — about to redesign something? Save the current version first.
- **At the end of each session** — include it in your "End of Session" routine.

A good habit is to ask Claude to commit (save a version) at the end of every work session.

---

## Part 17: Troubleshooting FAQ

Common problems and how to fix them.

---

**"Claude seems to have forgotten everything about my project"**

This usually happens when you start a new conversation. Claude doesn't automatically carry over everything — but your config files help.

*Fix:* Start the conversation with the "Get Up to Speed" prompt from Part 7. Make sure your CLAUDE.md and Context.md are up to date.

---

**"Claude won't read my files"**

Claude Code needs to be opened from within your project folder to access the files.

*Fix:* Make sure you opened Claude Code from the right folder. In Terminal, navigate to your project folder first:
```
cd ~/Sites/my-project-name
```
Then launch Claude Code from there.

---

**"Skills aren't loading or working"**

Skills need to be in the right folder, and Claude Code sometimes needs a fresh start to pick them up.

*Fix:* 
1. Check they're installed: ask Claude "List everything in the ~/.claude/skills/ folder"
2. If they're there but not working, start a new conversation
3. If they're not there, re-run the install command from Part 2

---

**"Claude keeps doing things I didn't ask for"**

Claude sometimes adds extra features, refactors code, or "improves" things beyond what you asked.

*Fix:* Add this to your CLAUDE.md:
> "Only do exactly what I ask. Don't add extra features, don't refactor code I didn't mention, don't make 'improvements' beyond the specific task. If you think something else should be changed, tell me and let me decide."

---

**"Claude is going in circles / keeps failing at the same thing"**

See Part 10 above for detailed options. The quick fix:

*Fix:* Say: "Stop. Let's take a completely different approach. What's the simplest possible way to achieve [your goal]?"

---

**"The install command failed"**

When you run `git clone` and get an error, it's usually one of these:

| Error | What It Means | Fix |
|-------|--------------|-----|
| "repository not found" | The web address is wrong or the repo moved | Search GitHub.com for the repo name to find the current address |
| "destination path already exists" | You already installed it | It's already there — no action needed |
| "command not found: git" | Git isn't installed on your computer | Ask Claude: "Help me install git on my Mac" |

---

**"I accidentally approved something I shouldn't have"**

If Claude made changes you didn't want:

*Fix:* If you've been using git (version control), say: "Undo the last change and go back to the previous version." If you haven't been using git, the changes may be harder to reverse — this is why Part 16 (backups) matters.

---

**"Claude is too slow"**

*Fix:* Try these, in order:
1. Make your requests shorter and more specific
2. Tell Claude: "Keep your responses short and to the point"
3. If it's doing research, tell it exactly where to look instead of searching broadly
4. Start a new conversation if the current one has been going for a very long time (long conversations use more processing)

---

**"I don't understand what Claude just did"**

*Fix:* Paste this any time:
```
Explain what you just did in plain, non-technical language. I'm not a developer.
```

---

## Part 18: Recommended Tools by Team

Each team in your business will get more out of Claude Code with different skills, repos, and MCP connections. Below is a tailored recommendation for each team.

**How to read this section:**
- **Skills** = playbooks that make Claude better at specific tasks (install once, works everywhere)
- **MCP Servers** = connectors that plug Claude into the apps your team already uses
- **Already connected** = things already set up in your current Claude Code environment

---

### SEO Team

**Skills to install:**

| Skill | What It Does | Where to Find It |
|-------|-------------|-----------------|
| **claude-seo** (AgriciDaniel) | 19 SEO sub-skills — technical audits, E-E-A-T, schema markup, backlinks, local SEO, AI/answer engine optimisation | github.com/AgriciDaniel/claude-seo |
| **Marketing Skills Library** (Corey Haines) | 5 SEO-specific skills plus content strategy, analytics, and CRO | github.com/coreyhaines31/marketingskills |
| **SEO & GEO Skills** (aaron-he-zhu) | 20 skills — keyword research, content writing, technical audits, rank tracking | github.com/aaron-he-zhu/seo-geo-claude-skills |

**Already installed:** seo-audit, programmatic-seo, ai-seo, content-strategy, audit-website, analytics-tracking

**MCP Servers to connect:**

| Server | What It Connects To | Where to Find It |
|--------|-------------------|-----------------|
| **Google Search Console** | Search performance data, indexing, crawl stats | github.com/AminForou/mcp-gsc |
| **Google Analytics 4** (Official Google) | Traffic, user behaviour, conversions | developers.google.com/analytics/devguides/MCP |
| **Ahrefs** (Official) | Backlinks, keyword metrics, brand monitoring | github.com/ahrefs/ahrefs-mcp-server |
| **Semrush** (Official) | SEO data, traffic analysis, market data | github.com/mrkooblu/semrush-mcp |
| **DataForSEO** | Search results, keyword metrics, backlinks, domain analytics | github.com/Skobyn/dataforseo-mcp-server |
| **Screaming Frog** | Site crawls, crawl data export | github.com/bzsasson/screaming-frog-mcp |

---

### PPC Team

**Skills to install:**

| Skill | What It Does | Where to Find It |
|-------|-------------|-----------------|
| **claude-ads** (AgriciDaniel) | 186 audit checks across Google, Meta, YouTube, LinkedIn, TikTok, and Microsoft Ads | github.com/AgriciDaniel/claude-ads |

**Already installed:** paid-ads, ad-creative

**MCP Servers to connect:**

| Server | What It Connects To | Where to Find It |
|--------|-------------------|-----------------|
| **Cross-Platform Ads** (amekala) | Google Ads, Meta Ads, LinkedIn Ads, TikTok Ads — 100+ tools in one server | github.com/amekala/ads-mcp |
| **Google Ads** (Official Google) | Campaign metrics, budgets, keyword analytics | developers.google.com/google-ads/api/docs/developer-toolkit/mcp-server |
| **Meta Ads** (pipeboard) | Facebook & Instagram ad management, budget optimisation, creative testing | github.com/pipeboard-co/meta-ads-mcp |
| **LinkedIn Ads** (RadiateB2B) | Campaign reviews, performance analysis, keyword planning | radiateb2b.com/linkedin-ads-mcp-server |

**Also useful:** github.com/jshorwitz/awesome-agentic-advertising — a curated list of every MCP server for advertising

---

### Web Developer Team

**Skills to install:**

| Skill | What It Does | Where to Find It |
|-------|-------------|-----------------|
| **Trail of Bits Security** | Security audits, vulnerability detection, CodeQL, Semgrep | github.com/trailofbits/skills |
| **Code Review Plugin** | Runs 4-5 parallel AI agents to review PRs for bugs and code quality | claude plugin install code-review@claude-plugins-official |

**Already installed:** test-driven-development, systematic-debugging, verification-before-completion, vercel-react-best-practices

**MCP Servers to connect:**

| Server | What It Connects To | Where to Find It |
|--------|-------------------|-----------------|
| **GitHub** (Official) | Repos, PRs, issues, code reviews, CI/CD | claude mcp add --transport http github https://api.githubcopilot.com/mcp/ |
| **Sentry** (Official) | Error tracking, performance monitoring, debugging | github.com/getsentry/sentry-mcp |
| **Playwright** | Browser testing — write tests, run them, screenshot failures | github.com/executeautomation/mcp-playwright |
| **PostgreSQL** | Query databases, health checks, index tuning | github.com/crystaldba/postgres-mcp |

**Already connected:** Vercel, PostHog

---

### Web Design Team

**Skills to install:**

| Skill | What It Does | Where to Find It |
|-------|-------------|-----------------|
| **63 Design Skills Collection** | Research, design systems, strategy, UI, interaction design, prototyping, testing, design ops | marieclairedean.substack.com (search "63 design skills") |
| **Wireframe Builder** | Generates wireframe prototypes as interactive HTML files | github.com/Magdoub/claude-wireframe-skill |
| **Accessibility Auditor** (claude-a11y-skill) | Comprehensive WCAG audits using axe-core | github.com/airowe/claude-a11y-skill |

**Already installed:** accessibility-review, design-system, design-critique, frontend-design, web-design-guidelines, ux-copy, design-handoff

**MCP Servers to connect:**

| Server | What It Connects To | Where to Find It |
|--------|-------------------|-----------------|
| **Figma** (Official) | Read designs, push code back as editable layers, get design tokens | claude plugin install figma@claude-plugins-official |
| **Framelink Figma** | Alternative — focused on giving coding agents design context for one-shot implementation | smithery.ai/servers/Zwe1/figma-context-mcp |

**Already connected:** Figma, Canva

---

### Client Services

**Skills to install:**

| Skill | What It Does | Where to Find It |
|-------|-------------|-----------------|
| **Claude Office Skills** | PPTX, DOCX, XLSX, PDF workflows with automation — great for client reports and proposals | github.com/tfriedel/claude-office-skills |

**Already installed:** copywriting, copy-editing, pptx, docx, xlsx, pdf, content-strategy, social-content

**MCP Servers to connect:**

| Server | What It Connects To | Where to Find It |
|--------|-------------------|-----------------|
| **Granola** (Meeting Notes) | Search meeting notes, extract action items and decisions | smithery.ai/servers/granola |
| **Google Docs** | Create and edit client reports and documents | github.com/a-bonus/google-docs-mcp |
| **Notion** (Official) | Client wikis, shared documents, project pages | claude mcp add --transport http notion https://mcp.notion.com/mcp |

**Already connected:** Slack, Gmail, Google Calendar, Google Drive, Canva, Monday.com

---

### Project Management

**Skills to install:**

No extra skills needed — you already have the key ones installed.

**Already installed:** senior-pm

**MCP Servers to connect:**

| Server | What It Connects To | Where to Find It |
|--------|-------------------|-----------------|
| **Linear** (Official) | Issue tracking integrated with dev workflow | claude mcp add --transport http linear https://mcp.linear.app/mcp |
| **Jira/Confluence** (Atlassian) | Tickets, sprints, documentation | github.com/atlassian/atlassian-mcp-server |
| **Asana** (Official) | Tasks, projects, assignments, progress tracking | claude mcp add --transport http asana https://mcp.asana.com/mcp |
| **ClickUp** (Official) | Task management, dependencies, time tracking | claude mcp add --transport http clickup https://mcp.clickup.com/mcp |
| **Notion** (Official) | Project docs, wikis, knowledge bases | claude mcp add --transport http notion https://mcp.notion.com/mcp |
| **Trello** | Board and card management | smithery.ai/servers/trello |

**Already connected:** Monday.com, Slack, Google Calendar

---

### Sales

**Skills to install:**

| Skill | What It Does | Where to Find It |
|-------|-------------|-----------------|
| **Marketing Skills Library** (Corey Haines) | Includes sales pod with positioning and CRO skills | github.com/coreyhaines31/marketingskills |

**Already installed:** copywriting (proposals), marketing-strategy-pmm (positioning, ICP), churn-prevention, pptx (pitch decks), docx, pdf, xlsx

**MCP Servers to connect:**

| Server | What It Connects To | Where to Find It |
|--------|-------------------|-----------------|
| **HubSpot** (Official) | Contacts, companies, deals, tickets, pipeline data | developers.hubspot.com/mcp |
| **Salesforce** (Official) | CRM data — 60+ tools, no code required | developer.salesforce.com (search "MCP") |
| **Apollo.io** | Search leads, enrich contacts, run email sequences | mcpmarket.com/server/apollo-io-3 |
| **LinkedIn Sales Navigator** | Search prospects, view profiles, send messages | github.com/globodai-group/mcp-linkedin-sales-navigator |
| **Alai** (Presentations) | Create pitch decks from discovery notes, export as PPTX/PDF | getalai.com/blog/mcp-server-for-presentations |

**Already connected:** Monday.com, Gmail, Google Calendar, Slack

---

### Finance

**Skills to install:**

| Skill | What It Does | Where to Find It |
|-------|-------------|-----------------|
| **Financial Analyst** | Ratio analysis, DCF valuation, budget variance, forecasts | github.com/alirezarezvani/claude-skills (finance folder) |
| **Invoice Organiser** | Scans receipts/invoices, extracts data, renames and categorises | github.com/ComposioHQ/awesome-claude-skills (invoice-organizer folder) |

**Already installed:** xlsx (spreadsheets), pdf (invoices/statements), docx (reports)

**MCP Servers to connect:**

| Server | What It Connects To | Where to Find It |
|--------|-------------------|-----------------|
| **Xero** (Official) | Invoicing, bank reconciliation, bookkeeping, financial reporting | github.com/XeroAPI/xero-mcp-server |
| **QuickBooks** (Official by Intuit) | Customers, invoices, expenses, reports | github.com/intuit/quickbooks-online-mcp-server |
| **Stripe** (Official) | Customers, invoices, subscriptions, refunds, disputes | docs.stripe.com/mcp |
| **Google Sheets** | Financial dashboards, reporting spreadsheets | smithery.ai/servers/googlesheets |
| **InvoiceFlow** | Create PDF invoices, predict late payments, auto-send reminders | glama.ai/mcp/servers (search InvoiceFlow) |

---

### Operations Director

**Skills to install:**

| Skill | What It Does | Where to Find It |
|-------|-------------|-----------------|
| **SOP Creator** | Turns brain dumps into clean Standard Operating Procedures | mcpmarket.com/tools/skills/sop-creator-for-ai-agents |
| **C-Level Advisory (COO)** | Operations strategy, board meetings, culture, team efficiency | github.com/alirezarezvani/claude-skills (c-level-advisor folder) |

**Already installed:** senior-pm, pptx, xlsx

**MCP Servers to connect:**

| Server | What It Connects To | Where to Find It |
|--------|-------------------|-----------------|
| **n8n** | Build and deploy workflow automations through natural language | docs.n8n.io (search "MCP server") |
| **Notion** (Official) | Process documentation, wikis, team knowledge bases | claude mcp add --transport http notion https://mcp.notion.com/mcp |
| **Airtable** | Databases with spreadsheet simplicity, workflow automation | smithery.ai/servers/airtable |
| **Databox** | Cross-platform KPI dashboards from 100+ data sources | smithery.ai/servers/Databox-MCP/databox |
| **Google Workspace** | Drive, Calendar, Gmail, Sheets, Docs, Slides — all in one | github.com/taylorwilsdon/google_workspace_mcp |

**Already connected:** Monday.com, Slack, Google Calendar, Google Drive

---

### Managing Director

**Skills to install:**

| Skill | What It Does | Where to Find It |
|-------|-------------|-----------------|
| **Business Strategy & Planning** | Ansoff, BCG, Porter's 5 Forces, Blue Ocean, SWOT frameworks | mcpmarket.com/tools/skills/business-strategy-planning-1 |
| **CEO Advisor** | Strategic decision-making, board decks, competitive intelligence, scenario planning | github.com/alirezarezvani/claude-skills (c-level-advisor folder) |
| **Deep Research** | Multi-phase investigation with source attribution | github.com/Weizhena/Deep-Research-skills |
| **Market Research** | Competitor analysis, industry trends, risk assessment | mcpmarket.com/tools/skills/market-research |

**Already installed:** startup-strategy-council, marketing-strategy-pmm, pptx

**MCP Servers to connect:**

| Server | What It Connects To | Where to Find It |
|--------|-------------------|-----------------|
| **HubSpot** (Official) | Pipeline data, revenue reporting, CRM | developers.hubspot.com/mcp |
| **Databox** | Cross-platform business KPIs from 100+ sources | smithery.ai/servers/Databox-MCP/databox |
| **Stripe** (Official) | Revenue data, payment activity, subscription metrics | docs.stripe.com/mcp |
| **Google Slides** | Board presentations | smithery.ai/servers/googleslides |
| **Notion** (Official) | Strategic documents, company wiki | claude mcp add --transport http notion https://mcp.notion.com/mcp |

**Already connected:** Monday.com, Slack, Google Calendar, Google Drive

---

### Technical Director

**Skills to install:**

| Skill | What It Does | Where to Find It |
|-------|-------------|-----------------|
| **Trail of Bits Security** | Security research, vulnerability detection, audit workflows | github.com/trailofbits/skills |
| **Security Auditor** | Structured security audits with remediation plans | github.com/wrsmith108/claude-skill-security-auditor |
| **Architect Reviewer** | Reviews architecture for technical, security, and compliance risks | github.com/VoltAgent/awesome-claude-code-subagents (architect-reviewer) |
| **Terraform Skill** (Anton Babenko) | Infrastructure as code — testing, modules, CI/CD patterns | github.com/antonbabenko/terraform-skill |
| **DevOps Skills** | AWS infrastructure, safety-first infrastructure patterns | github.com/lgbarn/devops-skills |

**Already installed:** test-driven-development, systematic-debugging, verification-before-completion

**MCP Servers to connect:**

| Server | What It Connects To | Where to Find It |
|--------|-------------------|-----------------|
| **Sentry** (Official) | Error tracking, performance monitoring | github.com/getsentry/sentry-mcp |
| **GitHub** (Official) | Repos, PRs, issues, code review | claude mcp add --transport http github https://api.githubcopilot.com/mcp/ |
| **PostgreSQL Pro** | Database health, query optimisation, schema intelligence | github.com/crystaldba/postgres-mcp |
| **Linear** | Engineering issue tracking, sprint management | claude mcp add --transport http linear https://mcp.linear.app/mcp |
| **Code Sentinel** | Finds security vulnerabilities, deceptive code, architectural issues | smithery.ai/servers/salrad/code-sentinel |

**Already connected:** Vercel, PostHog

---

### Internal Brand Marketing

**Skills to install:**

| Skill | What It Does | Where to Find It |
|-------|-------------|-----------------|
| **Marketing Skills Library** (Corey Haines) | Content, CRO, growth, and channels — full marketing toolkit | github.com/coreyhaines31/marketingskills |
| **OpenClaudia Skills** | 34+ marketing skills including social, email, content, growth | github.com/OpenClaudia/openclaudia-skills |

**Already installed:** copywriting, copy-editing, social-content, content-strategy, marketing-ideas, x-twitter-growth, marketing-psychology, brainstorming, banner-creator, video-editing, free-tool-strategy

**MCP Servers to connect:**

| Server | What It Connects To | Where to Find It |
|--------|-------------------|-----------------|
| **Buffer** | Social media scheduling | github.com/tn819/buffer-mcp |
| **Ayrshare** | Post to 13+ platforms (Twitter, Facebook, Instagram, LinkedIn, TikTok, YouTube, etc.) | ayrshare.com |

**Already connected:** Canva, Figma, Slack, Gmail, Google Drive

---

### Useful Across All Teams

| Server | What It Does | Where to Find It |
|--------|-------------|-----------------|
| **Zapier MCP** | Bridges to 8,000+ apps — great fallback if a dedicated MCP doesn't exist | zapier.com/mcp |
| **Google Workspace** (all-in-one) | Drive, Calendar, Gmail, Sheets, Docs, Slides, Forms, Tasks | github.com/taylorwilsdon/google_workspace_mcp |
| **Notion** (Official) | Documents, wikis, databases — useful for every team | claude mcp add --transport http notion https://mcp.notion.com/mcp |

---

## Part 19: Recommended Resources, People to Follow, and Learning

### Official Resources

| Resource | Who It's For | What It Is |
|----------|-------------|------------|
| **Claude Code Docs** (code.claude.com/docs) | Everyone | The official documentation — installation, features, workflows, memory, skills, and more. The best starting point. |
| **Claude Blog** (claude.com/blog) | Everyone | Official announcements, feature launches, and how-to articles from Anthropic |
| **MCP Introduction** (modelcontextprotocol.io) | Technical Director, Web Dev | Explains what MCP is and how it works — developer-focused |
| **Claude Platform Docs** (platform.claude.com/docs) | Web Dev, Technical Director only | API and Agent SDK documentation — for building custom software with Claude |
| **Anthropic's "Claude Code in Action"** | Everyone | Free official course — the authoritative foundation from the team that built it |

### People to Follow on X (Twitter)

These are the people who consistently share the most useful Claude Code content.

**The Builders (Inside Anthropic):**

| Who | X Handle | Why Follow Them |
|-----|----------|----------------|
| **Boris Cherny** | @bcherny | The creator of Claude Code. Shares his own setup, workflows, and tips directly from the Claude Code team. His #1 tip: always start in Plan Mode and use git worktrees for parallel sessions. |
| **Alex Albert** | @alexalbert__ | Anthropic's prompt engineering lead. If you want to understand how to talk to Claude better, this is your person. |
| **Thorsten Ball** | @thorstenball | Anthropic engineer who shares practical Claude Code insights from inside the team. |

**The Educators & Power Users:**

| Who | X Handle | Why Follow Them |
|-----|----------|----------------|
| **Jesse Vincent** | @obra | Created the Superpowers repo. Shares advanced configurations, custom commands, and power-user workflows. One of the earliest Claude Code experts. |
| **Corey Haines** | @coreyhainesco | Marketing and business angle on Claude Code. Created the Marketing Skills Library. Great for non-developers. |
| **Peter Steinberger** | @steipete | iOS developer legend now building AI coding tools. His blog (steipete.me) is required reading for anyone serious about agentic engineering. |
| **Nick Dobos** | @NickADobos | Curates and shares the best Claude Code repos, skills, and tools. Good for staying up to date on what's new. |
| **Matt Shumer** | @mattshumer_ | Pushes the boundaries of AI agent workflows. Shares advanced Claude Code setups for complex tasks. |
| **Simon Willison** | @simonw | Prolific tech blogger who covers AI coding tools with deeply technical, fair-minded analysis. |
| **Swyx (Shawn Wang)** | @swyx | Big-picture thinking about where AI coding tools are heading. Runs the Latent Space podcast. |
| **Greg Isenberg** | @gregisenberg | Business and startup angle — shares how to use Claude Code to build products quickly. |

### YouTube Channels

| Channel | What They Cover | Best For |
|---------|----------------|----------|
| **Fireship** (Jeff Delaney) | Fast-paced explainers when new Claude features drop. 3M+ subscribers. | Quick overviews — understand new features in minutes |
| **Theo (t3.gg)** | Honest takes on AI coding tools. His "I'm addicted to Claude Code" video is a great intro. ~500K subscribers. | Understanding what Claude Code actually feels like to use |
| **IndyDevDan** | Hands-on tutorials on building AI agents with Claude Code. Focuses on MCP and practical implementation. | Step-by-step building tutorials |
| **McKay Wrigley** | "Claude Code Deep Mastery" playlist — goes beyond basics into advanced agentic coding. | Going from beginner to advanced |
| **Chris Raroque** | In-depth breakdowns of how Claude handles memory, tokens, and agent behaviour. Ships real apps with Claude Code. | Understanding how Claude thinks |
| **Nataly Merezhuk** | "Vibe coding" from a software engineer's perspective. Practical tips, setup guides, avoiding common mistakes. | Practical daily usage tips |

### Newsletters & Blogs

| Resource | What It Is |
|----------|-----------|
| **Claude Developer Newsletter** (sign up at claude.com) | Official product updates, how-tos, and community spotlights from Anthropic |
| **ClaudeWorld Weekly** (claude-world.com/newsletter) | Community newsletter covering Claude Code news, tips, and new tools |
| **The Code Newsletter** (codenewsletter.ai) | Read by 200K+ developers — includes Claude Code guides and engineering resources |
| **Art of Saience** (newsletter.artofsaience.com) | Covers Claude Code best practices, reasoning models, and AI coding patterns |
| **ClaudeLog** (claudelog.com) | Docs, guides, tutorials, and best practices — a one-stop reference site |
| **HowAIWorks.ai** (howaiworks.ai) | "The Ultimate Resource Collection" — curated repos, tutorials, and learning paths |
| **MKT1 Newsletter** (newsletter.mkt1.co) | Marketing-focused — features real marketers showing what they've built with Claude Code |

### Free Learning Resources

| Resource | What It Is |
|----------|-----------|
| **Anthropic's "Claude Code in Action"** | Official free course from the team that built Claude Code |
| **freeCodeCamp Claude Code Handbook** | Free comprehensive guide |
| **Claude World Complete Guide** | Free community-written guide |
| **Scrimba Claude Code Tutorials** (scrimba.com) | Interactive coding tutorials |

### Key Articles Worth Bookmarking

| Article | Why It's Worth Reading |
|---------|----------------------|
| **"Claude Code Best Practices: Inside the Creator's 100-Line Workflow"** (mindwiredai.com) | Boris Cherny's actual CLAUDE.md file and how the creator of Claude Code uses it daily |
| **"Who to Follow If You're Serious About Claude Code"** (JP Caparas on Medium) | Curated list of 20 people across X, YouTube, and newsletters |
| **"What 4 Gen Marketers Are Building with Claude Code"** (MKT1 Newsletter) | Real marketing use cases — relevant for your marketing and client services teams |

---

## Part 20: Installation Status

Use this to track what you've installed. Update it as you go. Copy the install command and paste it into Terminal.

### Repos (Add-Ons)

| Item | Type | Status | What It Does | Install Command |
|------|------|--------|-------------|----------------|
| Superpowers | Repo | INSTALLED | Better planning, brainstorming, and quality | `git clone https://github.com/obra/superpowers.git ~/.claude/skills/superpowers` |
| Everything Claude Code | Repo | Not yet | Pre-built starter kit | `git clone https://github.com/anthropics/everything-claude-code.git ~/.claude/skills/everything-claude-code` |
| UI UX Pro Max | Repo | Not yet | Professional web design | `git clone https://github.com/nicholasoxford/ui-ux-pro-max.git ~/.claude/skills/ui-ux-pro-max` |
| Browser Use | Repo | Not yet | Claude can use a web browser | `git clone https://github.com/browser-use/browser-use.git ~/.claude/skills/browser-use` |
| claude-mem | Repo | Not yet | Enhanced memory | `git clone https://github.com/sdairs/claude-mem.git ~/.claude/skills/claude-mem` |

### Skills

| Item | Type | Status | What It Does | Install Command |
|------|------|--------|-------------|----------------|
| Marketing Skills Library | Skill | Not yet | Full marketing toolkit — copywriting, SEO, ads, social | `git clone https://github.com/coreyhaines31/marketingskills.git ~/.claude/skills/marketingskills` |
| Jobs to Be Done | Skill | Not yet | Customer research framework | Search skillsmp.com for "jobs to be done" |
| Explain Code (Official) | Skill | Not yet | Code-to-plain-English translator | Search claude.com/plugins for "explain code" |
| Deep Research | Skill | Not yet | Thorough multi-source research | `git clone https://github.com/Weizhena/Deep-Research-skills.git ~/.claude/skills/deep-research` |
| Web Assets Generator | Skill | Not yet | Create web and social images | Search skillsmp.com for "web assets generator" |
| claude-seo | Skill | Not yet | 19 SEO sub-skills — audits, E-E-A-T, schema, backlinks | `git clone https://github.com/AgriciDaniel/claude-seo.git ~/.claude/skills/claude-seo` |
| claude-ads | Skill | Not yet | 186 ad audit checks — Google, Meta, LinkedIn, TikTok | `git clone https://github.com/AgriciDaniel/claude-ads.git ~/.claude/skills/claude-ads` |
| Claude Office Skills | Skill | Not yet | PPTX, DOCX, XLSX, PDF workflows | `git clone https://github.com/tfriedel/claude-office-skills.git ~/.claude/skills/claude-office-skills` |
| Trail of Bits Security | Skill | Not yet | Security audits, vulnerability detection | `git clone https://github.com/trailofbits/skills.git ~/.claude/skills/trailofbits-security` |
| Business Strategy | Skill | Not yet | Porter's 5 Forces, SWOT, BCG, Blue Ocean | Search mcpmarket.com for "business strategy planning" |
| CEO Advisor | Skill | Not yet | Strategic decisions, board decks, competitive intel | `git clone https://github.com/alirezarezvani/claude-skills.git ~/.claude/skills/alirezarezvani-skills` |
| SOP Creator | Skill | Not yet | Turns brain dumps into clean SOPs | Search mcpmarket.com for "sop creator" |
| Financial Analyst | Skill | Not yet | Ratio analysis, DCF, budget variance, forecasts | Included in alirezarezvani/claude-skills above |

### MCP Servers (App Connectors)

These connect Claude to other apps. Paste the install command into Claude Code (not Terminal).

| Item | Type | Status | What It Connects To | Install Command |
|------|------|--------|-------------------|----------------|
| n8n | MCP | Not yet | Workflow automations (like Zapier) | `claude mcp add n8n -- npx @n8n/mcp-server` |
| Google Search Console | MCP | Not yet | Search performance, indexing | `git clone https://github.com/AminForou/mcp-gsc.git ~/.claude/skills/mcp-gsc` |
| Google Analytics 4 | MCP | Not yet | Traffic, user behaviour, conversions | See developers.google.com/analytics/devguides/MCP |
| Ahrefs | MCP | Not yet | Backlinks, keyword metrics | See github.com/ahrefs/ahrefs-mcp-server |
| Semrush | MCP | Not yet | SEO data, traffic analysis | See github.com/mrkooblu/semrush-mcp |
| Cross-Platform Ads | MCP | Not yet | Google, Meta, LinkedIn, TikTok ads | See github.com/amekala/ads-mcp |
| GitHub | MCP | Not yet | Repos, PRs, issues, CI/CD | `claude mcp add --transport http github https://api.githubcopilot.com/mcp/` |
| Sentry | MCP | Not yet | Error tracking, performance | See github.com/getsentry/sentry-mcp |
| Linear | MCP | Not yet | Issue tracking for dev teams | `claude mcp add --transport http linear https://mcp.linear.app/mcp` |
| Notion | MCP | Not yet | Docs, wikis, databases | `claude mcp add --transport http notion https://mcp.notion.com/mcp` |
| Asana | MCP | Not yet | Tasks, projects, progress tracking | `claude mcp add --transport http asana https://mcp.asana.com/mcp` |
| ClickUp | MCP | Not yet | Task management, time tracking | `claude mcp add --transport http clickup https://mcp.clickup.com/mcp` |
| HubSpot | MCP | Not yet | CRM — contacts, deals, pipeline | See developers.hubspot.com/mcp |
| Salesforce | MCP | Not yet | CRM — 60+ tools | See developer.salesforce.com (search MCP) |
| Xero | MCP | Not yet | Invoicing, bookkeeping, reporting | See github.com/XeroAPI/xero-mcp-server |
| QuickBooks | MCP | Not yet | Customers, invoices, expenses | See github.com/intuit/quickbooks-online-mcp-server |
| Stripe | MCP | Not yet | Payments, subscriptions, refunds | See docs.stripe.com/mcp |
| Databox | MCP | Not yet | KPI dashboards from 100+ sources | See smithery.ai/servers/Databox-MCP/databox |
| Granola | MCP | Not yet | Meeting notes, action items | See smithery.ai/servers/granola |
| Google Workspace | MCP | Not yet | Drive, Calendar, Gmail, Sheets, Docs — all in one | See github.com/taylorwilsdon/google_workspace_mcp |
| Zapier | MCP | Not yet | Bridges to 8,000+ apps — great fallback | See zapier.com/mcp |

### Already Connected (No Action Needed)

These are already set up in your current Claude Code environment:

| Item | Type | What It Connects To |
|------|------|-------------------|
| Monday.com | MCP | Project management boards |
| Canva | MCP | Design generation and editing |
| Figma | MCP | Design files, tokens, screenshots |
| Slack | MCP | Messages, channels, search |
| Gmail | MCP | Email, drafts, search |
| Google Calendar | MCP | Events, scheduling, free time |
| Google Drive | MCP | Files and shared drives |
| Vercel | MCP | Deployments, build logs |
| PostHog | MCP | Analytics, feature flags |
| PDF Tools | MCP | Read, create, merge PDFs |
| Chrome Control | MCP | Browser automation |
| Desktop Commander | MCP | File system, processes |
