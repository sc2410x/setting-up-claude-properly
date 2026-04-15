# MCP Install Instructions — Claude Desktop Custom Connectors

Quick reference for adding MCP servers to Claude Desktop. Keep this open as you work through them.

---

## How to Add Any Custom Connector

1. Open **Claude Desktop**
2. Click **Settings** (bottom-left)
3. Click **Connectors**
4. Scroll down and click **"Add custom connector"**
5. Fill in the **Name** and **URL** from the tables below
6. Click **Add**
7. Click **Connect** on the new entry
8. Sign in with your account for that service

---

## SEO & Marketing

| Name | URL | For Which Team |
|---|---|---|
| **Semrush** | `https://mcp.semrush.com/v1/mcp` | SEO |
| **Ahrefs** | `https://mcp.ahrefs.com/mcp` | SEO |
| **Otter.ai** | `https://mcp.otter.ai/mcp` | Client Services, PM |

---

## Google Marketing Stack — Honest Assessment

**TL;DR — There is no truly free option for Desktop that works forever.**

All third-party hosted wrappers have free tiers with limits that you'll likely hit. The official Google MCPs are free forever but only work with Claude Code CLI (not Desktop).

### Free Tiers (limited, will eventually need paid plan)

| Service | Free Limit | Cost After |
|---|---|---|
| **Stape** (GA4 + GTM) | 10,000 requests/month | £20+/month |
| **HireOtto** (Google Ads) | Limited queries | Paid tier |
| **Windsor.ai** (all-in-one) | 1 data source, basic data | Paid tier |

### Truly Free Forever (but requires Claude Code CLI)

| Option | Cost | Setup Difficulty |
|---|---|---|
| **Official Google MCPs** (GA4, GSC, Google Ads) | £0 forever | Medium — needs Terminal, OAuth creds |
| **Self-hosted open-source** | £0 forever | Medium — needs Terminal |

### Current Recommendation

**Skip the Google Marketing MCPs for now.** Here's why:

1. You already have **Semrush + Ahrefs** (flat-rate subscriptions you already pay for) which cover most SEO data needs
2. The free tier Google options have usage limits that will catch you out
3. The truly free options require Claude Code CLI, not Desktop

**When you actually need GA4 / GSC / Google Ads data in Claude:**
- Revisit this — we can install the Claude Code CLI and set up the free official Google MCPs then
- Or bite the bullet and pay for Windsor.ai (easiest — one connector covers everything, around £15-30/month)

### If You Want to Try the Free Tier Anyway

Only add these if you're OK with hitting limits eventually:

| Name | URL | Provider |
|---|---|---|
| Google Analytics 4 (Stape free tier) | `https://mcp-ga.stape.ai/mcp` | Stape — needs Stape account |
| Google Tag Manager (Stape free tier) | `https://gtm-mcp.stape.ai/mcp` | Stape — same account as above |
| Google Ads (HireOtto free tier) | `https://googleads.hireotto.com/mcp` | HireOtto — needs account |

**Google Search Console** — No good hosted option exists. Use Semrush data instead for now.

---

## Development & Project Management

| Name | URL | For Which Team |
|---|---|---|
| **GitHub** | `https://api.githubcopilot.com/mcp/` | Web Dev |
| **Notion** | `https://mcp.notion.com/mcp` | Everyone |
| **Linear** | `https://mcp.linear.app/mcp` | Web Dev, PM |
| **Asana** | `https://mcp.asana.com/mcp` | PM, Client Services |
| **ClickUp** | `https://mcp.clickup.com/mcp` | PM |

---

## Business & Finance

| Name | URL | For Which Team |
|---|---|---|
| **Stripe** | Check `docs.stripe.com/mcp` for current URL | Finance, Managing Director |
| **Xero** | Check `github.com/XeroAPI/xero-mcp-server` for URL | Finance |
| **HubSpot** | Check `developers.hubspot.com/mcp` for URL | Sales, Managing Director |

---

## Important Notes

### Requirements
- You need **Claude Pro plan or higher** — custom connectors aren't available on Free
- Each service needs its own valid subscription (e.g., Semrush needs a paid Semrush account)

### For SEO MCPs specifically
- **Semrush** — Needs Semrush One, SEO Pro, Guru, or Trends API subscription
- **Ahrefs** — Needs Ahrefs API access (usually Enterprise plan)

### Already in the Desktop Connectors panel
Some of these may appear as **pre-built connectors** in the Connectors search. Always search first before adding as custom — pre-built ones are simpler to set up.

### Good news
Connectors added this way are **global** — they work in every project and conversation across Claude Desktop on your Mac. You only add each one once.

---

## Already Connected (from Desktop Connectors Panel)

These are already working across all your projects:

| Connector | Purpose |
|---|---|
| Monday.com | Project management boards |
| Canva | Design generation |
| Figma | Design files, tokens |
| Slack | Messages, channels |
| Gmail | Email, drafts |
| Google Calendar | Events, scheduling |
| Google Drive | Files and folders |
| Vercel | Deployments, build logs |
| PostHog | Analytics, feature flags |
| Chrome Control | Browser automation |
| PDF Tools | Read, merge, split PDFs |
| Desktop Commander | File system access |

---

## Installation Order — My Recommendation

Start with the ones most useful day-to-day:

1. **Semrush** — SEO Team will use daily
2. **Ahrefs** — SEO Team will use daily
3. **Otter.ai** — Client Services for meeting notes
4. **Notion** — If your teams use Notion for docs
5. **GitHub** — Web Dev team
6. **Linear** or **Asana** or **ClickUp** — depending on what your PM team uses

After each one:
- Come back to Claude Code (this window)
- Tell me you've added it
- I'll help you test it works

---

## Troubleshooting

### "Can't see Add Custom Connector button"
- You might be on Claude Free — upgrade to Pro
- Update Claude Desktop to the latest version

### "Connection failed after signing in"
- The service may not allow the required API access on your plan
- Check the service's documentation for their MCP requirements

### "It's there but not responding"
- Try disconnecting and reconnecting
- Fully quit Claude Desktop (Cmd + Q) and reopen
