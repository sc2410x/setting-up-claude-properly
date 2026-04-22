# Decision Log

A running record of decisions made for this project. New decisions added to the top.

## Template

```
## YYYY-MM-DD — [Decision Title]

**Context:** What prompted this decision?
**Decision:** What did we decide?
**Alternatives considered:** What else was on the table?
**Trade-offs:** What are we giving up?
**Owner:** Who's responsible for it going forward?
**Review date:** When will we revisit?
```

---

## 2026-04-22 — Trello task routing via Smithery

**Context:** Needed a way to dump tasks from Claude conversations into Trello without switching contexts.
**Decision:** Connect Trello via Smithery's hosted MCP in Claude Desktop. Default board: Tasks. Always ask which list before creating a card.
**Alternatives considered:** Composio (simpler UX but extra signup), manual copy-paste into Trello.
**Trade-offs:** Depends on Smithery staying online. Minor.
**Owner:** Scott
**Review date:** 2026-07-01

---

## 2026-04-15 — Account routing rules

**Context:** Risk of deploying TDM client work to personal accounts or vice versa.
**Decision:** Always ask "TDM or personal?" before any deploy, database, or cloud action. Documented in global CLAUDE.md.
**Alternatives considered:** Separate Claude installations per account (too complex).
**Trade-offs:** Extra question on every deploy. Worth it.
**Owner:** Scott
**Review date:** Ongoing

---

## 2026-04-15 — Desktop only, skip Claude Code CLI

**Context:** Claude Code CLI offers some features Desktop doesn't, but adds complexity.
**Decision:** Use Claude Desktop only. All MCPs via Settings > Customize > Connectors.
**Alternatives considered:** Install CLI for scheduled tasks and free Google MCPs.
**Trade-offs:** Skip agent teams and some advanced features. Acceptable for current use.
**Owner:** Scott
**Review date:** When agent teams become genuinely useful

---

## 2026-04-08 — Three-step new project process

**Context:** Claude was diving into implementation before understanding requirements.
**Decision:** Every new project follows Understand > Spec > Plan before building starts.
**Alternatives considered:** Lighter-weight approval gates.
**Trade-offs:** Slower start, but fewer rewrites.
**Owner:** Scott (enforces by reading it back), Claude (follows it)
**Review date:** Review after 3 major projects

---
