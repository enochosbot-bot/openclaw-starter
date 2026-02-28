# ops/in-flight.md — Active Dispatch Tracker
_Main agent maintains this file. Updated at dispatch and on close._

## Active

| Task | Agent | Dispatched | Expected Close | Notes |
|------|-------|------------|----------------|-------|

## Completed (last 7 days)

| Task | Agent | Dispatched | Closed | Result |
|------|-------|------------|--------|--------|

---

## Rules
- Every dispatch → add a row to Active immediately
- Every close → move row to Completed, add result summary
- If Active row is >60min old → heartbeat flags it to user
- Never leave a row in Active after work is confirmed done
