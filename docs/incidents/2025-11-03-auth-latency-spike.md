---
date: "2025-11-03"
severity: "sev-3"
status: "resolved"
resolved_at: "2025-11-03"
duration_minutes: 25
postmortem_url: "https://docs.pantalasa.org/incidents/2025-11-03-auth-latency-spike"
postmortem_complete: true
commander: "mick@pantalasa.org"
services_affected: ["auth"]
customer_impact: "minimal"
---

# Incident: Auth service p99 latency spike

## Summary

At 2025-11-03 09:12 UTC, `auth` service p99 latency spiked from ~80ms to ~2s. Caused by an accidentally-deployed debug-logging flag that was writing to a synchronous stdout. Fixed-forward with a new deploy at 09:37 UTC.

## Timeline

- 09:12 UTC — Alert: p99 latency > 1s.
- 09:14 UTC — Ack.
- 09:25 UTC — Identified recent deploy with debug logging enabled.
- 09:37 UTC — Fixed-forward deploy restored baseline latency.

## Customer Impact

Minimal. p99 affected but p50 stayed normal; few customers noticed.

## Action Items

All closed as of 2025-11-20:
- [x] Debug flag now guarded by env var with a CI check preventing deploy-to-prod with it on.
- [x] Synchronous-logging lint rule added to internal linter.
