# Verification Protocol
_Never mark a task complete without verifying the actual deliverable, live._

## Core Rule
"File exists on disk" is not verification. "Sub-agent said done" is not verification.

## General Verification Standards

| Claim | Verification Required |
|-------|-----------------------|
| File was created | `test -f <path>` AND read first 10 lines |
| Sub-agent completed | Check output. Read the file. Don't trust the announcement. |
| Config change applied | Read the live config file |
| Cron job works | `openclaw cron list` — confirm job exists |
| Git committed | `git log --oneline -1` — confirm hash |
| Deploy went live | HTTP 200 from production URL |

## Website Deployments

After ANY website task — new page, nav change, content update:

1. Verify file exists locally
2. Hit the live URL: `curl -o /dev/null -s -w "%{http_code}" https://[your-domain]/[path]` — must return 200
3. If not live, deploy immediately, then re-verify
4. Never report live based on local file existence alone

## Sub-Agent Completion Checks

1. Output tokens < 500 on a complex task → assume nothing was written, verify manually
2. Read the primary deliverable — don't trust the summary
3. For code: does it actually run?
4. For deploys: hit the live URL
5. For config: read the file, confirm the change is there

## Auth & Environment

After any session restart or compaction:
- Re-verify auth before API calls
- Re-verify working directory
- Re-verify required files exist
