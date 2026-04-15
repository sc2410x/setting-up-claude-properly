# Pre-Install Checklist — Don't Install the Wrong Thing
**Use this before installing any new Claude tool, skill, repo, or MCP.**

---

## The 4 Types of Claude Tools (and how to tell them apart)

| Type | What It Is | Where It Lives | How Claude Uses It |
|------|-----------|----------------|-------------------|
| **Skill** | A playbook for specific tasks | `~/.claude/skills/` | Auto-loaded, picked by prompt |
| **Repo / Skill Collection** | A bundle of multiple skills | `~/.claude/skills/` | Same — each sub-skill auto-loaded |
| **MCP Server** | A connector to another app | Claude Desktop Connectors OR `~/.claude/mcp.json` | Claude uses when it needs that app's data |
| **CLI Tool** | A standalone program | Anywhere (not `/skills/`) | You run it in Terminal yourself |

---

## Before Installing Anything, Ask:

### Step 1: What type is it?

Look at the GitHub repo README for these clues:

| Clue in the README | It's probably... |
|---|---|
| "Install to `~/.claude/skills/`" | A **Skill** |
| Contains `SKILL.md` file at root | A **Skill** |
| Contains `/skills/` subfolder with SKILL.md files inside | A **Skill collection (Repo)** |
| "MCP server" or "install via `claude mcp add`" | An **MCP Server** |
| "Connect to Claude Desktop" with a URL | An **MCP Server** (for Desktop) |
| "Run `npx toolname`" or "npm install -g" or has a `bin` in package.json | A **CLI Tool** (probably doesn't belong in /skills/) |
| Contains `plugins/` folder or `.claude-plugin.json` | A **Plugin** (different install method) |
| Uses `skill.json` (lowercase) instead of `SKILL.md` | Antigravity format — **won't work in Claude Code** |

### Step 2: Verify the format

**For a Skill:** Check the repo has either:
- ✅ `SKILL.md` at the root (single skill), OR
- ✅ `/skills/<name>/SKILL.md` structure (multiple skills)

**For an MCP:** Check:
- ✅ It provides a URL like `https://mcp.example.com/mcp` (works in Desktop + CLI), OR
- ✅ It provides an `npx` command (CLI only)

**For a Claude Desktop Connector:** Check:
- ✅ Is it in the official Connectors panel? (Settings → Connectors → search)
- ✅ If not official, is there a public MCP URL for "Add custom connector"?

### Step 3: Check what it supports

The repo should say which of these it works with:
- ✅ Claude Code
- ⚠️ Only Claude Desktop (Cowork) — different install method
- ⚠️ Only Antigravity / Cursor / Codex — won't work in Claude Code
- ⚠️ Only a specific platform (e.g., VS Code extension)

---

## Quick Decision Tree

```
Is it a GitHub repo?
├── Yes → Check its structure
│   ├── Has SKILL.md at root? ────────────────→ Install as Skill
│   ├── Has /skills/ subfolder?───────────────→ Install as Skill (collection)
│   ├── Has plugins/ folder? ─────────────────→ Install as Plugin (different process)
│   ├── Has package.json with bin field? ─────→ It's a CLI tool — NOT a skill
│   └── Uses skill.json (lowercase)? ─────────→ Wrong format — won't work
│
└── Is it an MCP URL?
    ├── Official connector (in Desktop UI)?───→ Add via Settings → Connectors
    └── Custom URL? ──────────────────────────→ Add via "Add Custom Connector"
```

---

## Common Mistakes I Made

**❌ "It cloned successfully, so it's installed."**
Cloning downloads files. That's not the same as Claude being able to use them.

**❌ "It's in `~/.claude/skills/` so it's a skill."**
If the repo is a CLI tool or a plugin, putting it in /skills/ doesn't make it a skill. The folder name doesn't matter — the contents do.

**❌ "MCP added to `~/.claude/mcp.json` so it works everywhere."**
That file is only read by the Claude Code CLI tool. The Claude Desktop app ignores it. For Desktop, MCPs need to be added via Settings → Connectors.

**❌ "The install command worked, so I'll update the status to INSTALLED."**
Don't mark something as installed until it's been tested. Ask Claude to use it and confirm the skill loads.

---

## Verification Test

After installing any skill, test it:

```
Paste this into Claude: "What skills do you have access to that relate to [topic]?"
```

If your newly-installed skill shows up in the response, it's working. If not, it's not properly installed.

For MCPs:

```
Paste this into Claude: "What MCP servers / app connectors do you have available?"
```

Claude should list the MCP by name.

---

## Rules for Future Installs

1. **Read the README first** before cloning
2. **Check the structure** — does it have SKILL.md in the right place?
3. **Understand what type it is** — skill vs CLI vs plugin vs MCP
4. **Install to the right place** — skills to `/skills/`, MCPs via Desktop UI
5. **Test it works** before marking as installed
6. **Update the install tracker honestly** — only mark INSTALLED once verified
