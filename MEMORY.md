# MEMORY.md — Long-Term Memory

## Who I Am
- **Name:** [agent name]
- **Born:** [first day online]
- **Human:** [operator name + Telegram handle]

## Infrastructure
- Mac mini (Darwin arm64) — primary host
- Telegram bot for all comms
- APIs configured: Anthropic (main model), OpenAI (STT/TTS, voice: onyx), ElevenLabs (voice)
- Tunneling: Tailscale preferred over ngrok (ngrok dies on restart)
- Google Drive: auto-backup every 6 hours

## Agent Architecture
- **Main** — command center, all DMs. Reads MEMORY.md every session.
- **Scribe (Ezra)** — research, writing, dossiers. Workspace: `~/.openclaw/workspace-scribe/`. No code, no comms, no config.
- **Coder (Bezzy)** — scripts, apps, site builds. Workspace: `~/.openclaw/workspace-coder/`. No research, no comms.
- **Researcher (Berean)** — web search, synthesis, daily briefs.
- **Observer (Gideon)** — security audits, nightly scans, health checks.
- **QA (Basher/Nehemiah)** — smoke tests, output QA after coder ships.

## Automation Stack
21 crons running. Key ones:
- **Mission Pulse** — 9/12/15/18/21 CST — proactive check-in when idle
- **Morning Brief** — 8AM daily
- **X Bookmarks Sync** — 4AM nightly
- **Nightly Maintenance + Security** — 3AM
- **Nehemiah QA** — smoke test at 6:30AM, output QA 3x/day
Full list: `ops/cron-registry.md`

## Key Integrations
- Obsidian (`~/Documents/Brain/`) — canon for all research, people, decisions
- Google Drive — workspace backup
- X/Twitter — daily bookmarks sync, OAuth active
- YouTube — upload pipeline, OAuth configured

## Lessons Learned
- Config patches defer during active replies — always restart after
- ngrok must be run fully detached (nohup + disown)
- Telegram forum topics need threadId param
- Long pasted content arrives in multiple messages — wait for the full thing before responding
- Tool errors in Telegram need immediate plain-English follow-up — no exceptions
- Obsidian is canon — research dies in chat, it lives in Brain/

## Operating Heuristics
1. **Context Recovery** — detect same-session / post-compaction / cold-start before searching
2. **Plan Validation** — check ENV, DEPS, STATE, FILES before any multi-step work
3. **Parallelization** — <3 files = single agent, >5 files = parallel agents

## Preferences
- No email crons
- Always verify live URL before reporting deploy done
- One comprehensive response per topic — don't repeat

## Queued Work
_(Move items here from ops/production-queue.md when in-progress)_
