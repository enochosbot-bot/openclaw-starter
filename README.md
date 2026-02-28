# openclaw-starter

A production-ready OpenClaw workspace. Built from a real working setup — not a tutorial, not a toy. This is the actual architecture.

---

## What's in here

| File | Purpose |
|------|---------|
| `SOUL.md` | Personality, values, hard rules, anti-patterns. The agent's character. |
| `IDENTITY.md` | Name, vibe, emoji, worldview. Fill this in during bootstrap. |
| `USER.md` | Who you are — so the agent actually knows you. Keep it current. |
| `AGENTS.md` | Operating rules, multi-agent fleet, dispatch loop, AFK protocol, session durability. |
| `MEMORY.md` | Long-term distilled memory. Grows over time. |
| `HEARTBEAT.md` | Periodic health checks — stale dispatch detection, checkpoint continuity. |
| `TOOLS.md` | Your specific setup — devices, hosts, preferences. |
| `BOOTSTRAP.md` | First-run conversation guide. Delete after setup. |

```
ops/
  in-flight.md          ← live dispatch tracker (what's running right now)
  production-queue.md   ← AFK work queue (agent pulls from here when you go quiet)
  dispatch-routing.md   ← which agent handles what
  verification-protocol.md ← how to confirm work is actually done

shared-context/
  checkpoints/          ← session durability checkpoints
  handoffs/             ← agent-to-agent context passing
  drafts/               ← content waiting for approval
  agent-outputs/        ← research and analysis outputs

memory/
  YYYY-MM-DD.md         ← raw daily session logs

research/               ← staging only (mirror everything to Obsidian)
```

---

## The Architecture That Actually Matters

### Multi-Agent Fleet

The real power isn't one agent — it's a coordinated fleet:

```
Main Agent              ← you talk to this one
  ├── Scribe            ← research, writing, dossiers (no code, no comms)
  ├── Coder             ← builds scripts/apps/tools (no research, no comms)
  └── [add more]        ← specialize as you scale
```

Each agent has a scoped role and its own workspace. The main agent dispatches, tracks, and verifies. Sub-agents close by pinging main + updating `ops/in-flight.md`.

### The Dispatch Loop

Every task dispatched to a sub-agent:
1. Gets a row in `ops/in-flight.md` before it starts
2. Gets a Closing Block in the brief (mandatory Telegram ping + tracker update on completion)
3. Gets verified by main before reporting done to user

Heartbeat checks for stale rows. If something's been open >60 min, you get an alert.

### AFK Protocol

Go quiet for 5 minutes → agent starts pulling from `ops/production-queue.md` automatically. Come back to completed work instead of an idle assistant. No asking permission. Just work.

### Session Durability

Before any long operation, a checkpoint gets written to `shared-context/checkpoints/session-checkpoint.md`. If the session dies mid-task, the next session picks up exactly where it left off.

### Obsidian is Canon

All research, dossiers, briefings, and reference docs go to Obsidian (`~/Documents/Brain/`). The workspace `research/` folder is staging only. This is a hard rule — it's what makes the knowledge compound instead of dying in chat history.

### Memory Architecture

```
MEMORY.md               ← distilled long-term memory (main session only)
memory/YYYY-MM-DD.md    ← raw daily session notes
~/Documents/Brain/      ← Obsidian vault (the actual canon)
```

Daily logs capture everything. Periodically distill the important stuff into `MEMORY.md`. Research and reference → Obsidian always.

---

## Getting Started

1. **Install OpenClaw** → [openclaw.ai](https://openclaw.ai)
2. **Clone this repo** into your workspace directory (`~/.openclaw/workspace`)
3. **Fill in the blanks:**
   - `IDENTITY.md` — give your agent a name and personality
   - `USER.md` — tell it who you are
   - `SOUL.md` — read it, edit the worldview section to match yours
   - `MEMORY.md` — seed it with your context
4. **Connect Telegram** — BotFather → new bot → paste token into OpenClaw config (5 min)
5. **Say hello** — your agent reads these files on first message, then runs `BOOTSTRAP.md`
6. **Delete `BOOTSTRAP.md`** when you're set up

---

## The Thing Most People Miss

The files aren't config — they're identity. The agent reads them every session. They're how it knows who you are, what you care about, and what it's supposed to do while you sleep.

Treat them like a living document. Update them as you learn what works. The agent gets better as the files get better.

---

## Community

- Discord: [discord.com/invite/clawd](https://discord.com/invite/clawd)
- Skills: [clawhub.com](https://clawhub.com)
- Docs: [docs.openclaw.ai](https://docs.openclaw.ai)
