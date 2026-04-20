---
policy_id: "POL-DH-001"
owner: "security@pantalasa.org"
last_reviewed: "2025-08-15"
next_review: "2026-08-15"
effective_date: "2024-06-01"
---

# Data Handling Policy

## Purpose

Defines how Pantalasa classifies, stores, transmits, retains, and disposes of data across all systems.

## Scope

Applies to all customer data, operational data, and internal records processed by Pantalasa infrastructure.

## Classifications

| Classification | Examples | Controls |
|----------------|----------|----------|
| Public | Marketing site content | None required |
| Internal | Runbooks, internal metrics | Access control on internal network |
| Confidential | Customer records, business metrics | Encryption at rest + in transit, quarterly access reviews |
| Restricted | Payment tokens, security keys | Plus: hardware-backed keys, audit logging, rotation |

## Retention

- Application logs: 30 days
- Audit logs: 2 years
- Customer data: per contract, default 7 years post-termination
- Backups: 90 days (short-term), 2 years (long-term)

## Disposal

All storage media holding Restricted data must be cryptographically wiped or physically destroyed per NIST SP 800-88 guidance upon decommissioning.

## Enforcement

Violations reviewed by Security. This policy is reviewed annually.
