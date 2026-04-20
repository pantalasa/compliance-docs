---
policy_id: "POL-CM-001"
owner: "engineering@pantalasa.org"
last_reviewed: "2025-11-10"
next_review: "2026-11-10"
effective_date: "2024-03-01"
---

# Change Management Policy

## Purpose

Describes how production changes are proposed, reviewed, approved, and rolled back at Pantalasa.

## Scope

Applies to every change to production infrastructure, customer-facing code, and data schemas.

## Policy

### Change categories

- **Standard change** — pre-approved, low risk, follows a runbook (e.g., routine dependency bumps with CI green).
- **Normal change** — requires PR review and CI pass; most code and config changes.
- **Emergency change** — outage mitigation; abbreviated review with post-hoc documentation within 48h.

### Required controls

- PR reviewed by at least one other engineer.
- CI green (lint, test, security scans).
- Deploy via GitOps pipeline with audit trail.
- Changes to Restricted-data paths require security-team approval.

### Rollback

Every deploy must be revertible by the next deploy (no one-way migrations without a documented rollback plan).

## Enforcement

Violations reviewed by Engineering leadership. This policy is reviewed annually.
