# openclaw-starter

A production-ready OpenClaw workspace template. Skip weeks of trial and error — clone this, fill in your details, and start with a fully-tuned agent setup from day one.

Built from a real working instance. This is the actual architecture, not a toy demo.

---

## What is this?

[OpenClaw](https://openclaw.ai) is a personal AI agent platform. It runs on your machine, connects to your tools, and talks to you via Telegram (or other channels). Think of it as a chief of staff that never sleeps.

This repo is the **workspace** — the files that define how your agent thinks, remembers, and operates. The workspace is the personality and memory layer on top of OpenClaw.

---

## The Core Idea

Your agent reads these files every session. They're its soul, memory, and operating manual.

| File | What it does |
|------|-------------|
| `SOUL.md` | Personality, values, hard rules, anti-patterns |
| `IDENTITY.md` | Name, vibe, emoji, worldview |
| `USER.md` | Who you are — so the agent actually knows you |
| `AGENTS.md` | Operating rules, memory architecture, sub-agent dispatch |
| `MEMORY.md` | Long-term distilled memory (updated over time) |
| `HEARTBEAT.md` | Periodic health checks — what to monitor automatically |
| `TOOLS.md` | Your specific setup — devices, hosts, preferences |
| `BOOTSTRAP.md` | First-run guide (delete after setup) |

---

## Memory Architecture

```
memory/
  YYYY-MM-DD.md          ← daily raw logs
  VAULT_INDEX.md         ← index for fast lookup
  decisions/             ← key decisions + why
  people/                ← people you work with
  lessons/               ← what didn't work
  commitments/           ← things promised
  preferences/           ← how you like things done
  projects/              ← project-level context

MEMORY.md                ← distilled long-term memory (the gold)
```

The pattern: daily logs capture everything → periodically promote the important stuff to typed memory → distill into `MEMORY.md`. The agent gets smarter over time instead of forgetting everything on restart.

---

## Sub-Agent Architecture

The real power comes from spawning specialized sub-agents:

```
Main Agent          ← you talk to this one
  ├── Research Agent  ← deep dives, dossiers, writing
  ├── Coder Agent     ← builds scripts/apps/tools
  └── Observer        ← background monitoring, health checks
```

Configure your agents in OpenClaw, then reference them in `AGENTS.md`. The dispatch loop in `ops/in-flight.md` tracks what's running and ensures nothing falls through the cracks.

---

## The AFK Protocol

One of the best features: when you go quiet for 5+ minutes, the agent starts working through `ops/production-queue.md` automatically. Come back to completed tasks instead of an idle assistant.

---

## Getting Started

1. **Install OpenClaw** → [openclaw.ai](https://openclaw.ai)
2. **Clone this repo** into your workspace directory (`~/.openclaw/workspace`)
3. **Fill in the placeholders:**
   - `IDENTITY.md` — give your agent a name and personality
   - `USER.md` — tell it who you are
   - `MEMORY.md` — seed it with your context
   - `SOUL.md` — read it, edit the worldview section to match yours
4. **Connect your channel** (Telegram is easiest — BotFather, 5 minutes)
5. **Say hello** — your agent reads these files on first message

---

## The Philosophy

**Your agent should feel like a person, not a product.**

The `SOUL.md` file is the key insight here. Most AI setups give you a generic assistant. This architecture gives you someone with opinions, memory, and a reason for existing. It pushes back when you're wrong. It remembers what you care about. It works while you sleep.

The files in this repo took months of iteration to land on. The memory architecture, the dispatch loop, the AFK protocol, the session durability rules — all of these came from running this in production every day.

---

## Community

- Discord: [discord.com/invite/clawd](https://discord.com/invite/clawd)
- Skills: [clawhub.com](https://clawhub.com)
- Docs: [docs.openclaw.ai](https://docs.openclaw.ai)
