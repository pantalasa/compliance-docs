---
date: "2025-05-08"
severity: "sev-3"
status: "resolved"
resolved_at: "2025-05-08"
duration_minutes: 42
postmortem_url: "https://docs.pantalasa.org/incidents/2025-05-08-elevated-5xx-rates"
postmortem_complete: true
commander: "brandon@pantalasa.org"
services_affected: ["backend"]
customer_impact: "partial"
---

# Incident: Elevated 5xx rates on backend

## Summary

At 2025-05-08 14:18 UTC, the `backend` service began returning elevated 5xx rates (~8% over baseline of <0.5%). Root cause was a connection-pool starvation introduced by a dependency update the previous day. Rolled back at 14:46 UTC; error rates returned to baseline by 15:00 UTC.

## Timeline

- 14:18 UTC — Alert fired (error rate > 5% for 2 minutes).
- 14:22 UTC — On-call paged, ack at 14:24.
- 14:32 UTC — Root cause identified (connection pool starvation).
- 14:46 UTC — Rollback complete.
- 15:00 UTC — Error rates at baseline.

## Customer Impact

~42 minutes of degraded response times. Estimated ~3% of requests returned 5xx.

## Action Items

All closed as of 2025-05-20:
- [x] Add connection-pool saturation alert (was missing).
- [x] Update dependency-update runbook to include pool-sizing check.
- [x] Staged-rollout for this category of dependency going forward.
