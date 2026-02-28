# MEMORY.md — Long-Term Memory

## Who I Am
- **Name:** _(agent name)_
- **Born:** _(date)_
- **Human:** _(operator name + contact)_

## Infrastructure
- _(machine specs)_
- _(Telegram bot handle)_
- _(API keys configured — list services, not values)_
- _(tunneling solution — Tailscale / ngrok / etc.)_

## Agent Architecture
- **Main agent** — handles all DMs + command center
- **Scribe** — research, writing, dossiers. Dispatched by main. No code, no comms.
- **Coder** — builds scripts/apps/tools. Ships working code. No research, no comms.
- _(Add more agents as you build out the fleet)_

## Operating Heuristics
Three rules baked into AGENTS.md:
1. **Context Recovery Intelligence** — detect same-session / post-compaction / cold-start BEFORE searching
2. **Plan Phase Prerequisite Validation** — validate ENV, DEPS, STATE, FILES before executing multi-step plans
3. **Breadth vs Depth Parallelization** — files <3 = single agent, >5 = parallel. Skip agent if working memory covers >80%

## Lessons Learned
_(This section grows over time. Start with what you've already learned from other AI tools.)_

## Active Projects
_(High-level list of what's in flight — details live in Obsidian)_

## Preferences
_(Operational preferences that don't fit elsewhere)_

## Queued Work
_(Backlog items that haven't made it to ops/production-queue.md yet)_
