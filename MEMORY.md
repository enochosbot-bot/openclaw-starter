# MEMORY.md — Long-Term Memory

_This file is distilled wisdom — not a daily log. Update it periodically from daily memory files._
_Fill in your own details as you go. This is your agent's brain._

## Who I Am
- **Name:** [AGENT_NAME]
- **Born:** [DATE]
- **Human:** [YOUR_NAME]

## [YOUR_NAME]
- Timezone: [TIMEZONE]
- [KEY PREFERENCES — how they communicate, what drains them, what they care about]
- "Stepping away" / "afk" / "//" = START WORKING on queued tasks immediately

## Infrastructure
- [YOUR_MACHINE] (OS, arch)
- Messaging channel: [TELEGRAM/SIGNAL/etc]
- API keys configured: [LIST SERVICES]

## Operating Heuristics
Three rules for consistent behavior:
1. **Context Recovery Intelligence** — detect same-session / post-compaction / cold-start BEFORE searching. Audit env/shell state after compaction.
2. **Plan Phase Prerequisite Validation** — validate [ENV], [DEPS], [STATE], [FILES] before executing multi-step plans.
3. **Breadth vs Depth Parallelization** — files <3 = depth (single agent), >5 = breadth (parallel). Skip agent if working memory covers >80%.

## Lessons Learned
_Add entries here as you discover what works and what doesn't._
- [LESSON 1]
- [LESSON 2]

## Agent Architecture
_Define your sub-agents here once you set them up._
- **[MAIN_AGENT]** — main agent, handles all topics + DMs
- **[RESEARCH_AGENT]** — spawnable sub-agent for research/writing/dossiers
- **[CODER_AGENT]** — coding agent, builds projects/scripts/apps

## Preferences
_Things the agent should never forget about how you operate._
- [PREFERENCE 1]
- [PREFERENCE 2]

## Queued Work
_Overflow from production queue. Things to pick up when idle._
- [TASK 1]
