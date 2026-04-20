---
date: "2026-01-22"
severity: "sev-2"
status: "resolved"
resolved_at: "2026-01-22"
duration_minutes: 18
postmortem_url: "https://docs.pantalasa.org/incidents/2026-01-22-database-failover"
postmortem_complete: true
commander: "brandon@pantalasa.org"
services_affected: ["backend", "inventory"]
customer_impact: "partial"
---

# Incident: Unplanned primary database failover

## Summary

At 2026-01-22 19:04 UTC, our primary PostgreSQL instance became unreachable (cloud provider hardware failure). Automatic failover to `replica-1` kicked in at 19:06 UTC. Full recovery at 19:22 UTC. Exercised the DR procedure successfully.

## Timeline

- 19:04 UTC — Primary unreachable, alerts fire.
- 19:06 UTC — Automatic failover initiated.
- 19:12 UTC — On-call paged and confirmed failover succeeded.
- 19:18 UTC — Applications reconnected; error rates trending down.
- 19:22 UTC — All services at baseline.

## Customer Impact

~18 minutes of partial unavailability on `backend` and `inventory`. Well within our RTO of 60 minutes.

## Action Items

All closed as of 2026-02-15:
- [x] Post-failover verification checklist updated based on gaps found.
- [x] Automated DNS update step (was manual, took 2 min of the downtime).
- [x] Confirmed cloud provider has applied hardware fix.

## Notes

This was the first real (non-exercise) failover since the DR plan was formalized. Exercise drill on 2026-03-15 incorporated lessons from this incident.
