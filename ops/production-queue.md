# Production Queue
_Pulled automatically when user goes AFK 5+ min. Main agent works top-to-bottom._

## Active

_(Add tasks here — agent will pick these up when you go quiet)_

## Parked

_(Tasks that need more info or have blockers)_

## Completed

_(Moved here when done)_

---

## How This Works

When you go quiet for 5+ minutes, the agent starts here. Tasks are pulled top-to-bottom.
Format each task with enough context that the agent can execute without asking.

**Good task:**
> Research the competitive landscape for [topic] — focus on pricing, positioning, and gaps. Output to Obsidian at Brain/Research/[topic]/competitive-landscape.md

**Bad task:**
> Do the thing we talked about

If a task needs a sub-agent, the main agent dispatches and tracks via `ops/in-flight.md`.
