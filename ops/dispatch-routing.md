# Dispatch Routing
_Which agent handles what. Update as your fleet grows._

## Task → Agent Routing

| Task Type | Agent | Notes |
|-----------|-------|-------|
| Code (features, fixes, scripts) | Coder | Always |
| Website changes | Coder | Must include deploy + live URL check in brief |
| Config changes | Coder | Never from chat — outage risk |
| Research tasks | Scribe | Web search, synthesis, deep dives |
| Writing / content | Scribe | Blog posts, social copy, docs |
| Everything else | Main | Handle directly |

## Mandatory Dispatch Protocol (ALL agents, every task)

### Before dispatching
1. Add a row to `ops/in-flight.md` → Active table
2. Include the Closing Block in every brief (see below)

### Closing Block (paste verbatim at end of every brief)
```
## Mandatory Close (do not skip)
When your work is fully done:
1. Update ops/in-flight.md — move your row from Active to Completed with result summary
2. Send a Telegram message confirming completion:
   message: "✅ [task name] — done. [1-sentence summary of what was shipped/produced]"
3. Do NOT mark done until both steps above are complete.
```

### After close
- Verify the ping arrived
- If agent went silent >60min: check sessions_history, surface status manually
