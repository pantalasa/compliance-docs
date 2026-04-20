---
vendor: "Amazon Web Services"
category: "cloud-provider"
last_assessed: "2026-01-10"
next_review: "2027-01-10"
soc2_on_file: true
soc2_report_date: "2025-09-30"
data_classification: "confidential"
criticality: "tier-1"
reviewer: "dane@pantalasa.org"
---

# Vendor Assessment — Amazon Web Services

## Summary

AWS is our primary cloud provider. All production compute, storage, and networking runs on AWS. Data stored includes customer records, payment metadata, and operational logs.

## Assessment

| Field | Value |
|-------|-------|
| Last assessed | 2026-01-10 |
| Next review | 2027-01-10 (annual) |
| SOC 2 on file | yes (Type II, report dated 2025-09-30) |
| ISO 27001 on file | yes |
| Data classification | confidential |
| Criticality | tier-1 |
| MSA in place | yes |
| DPA in place | yes |

## Data processed

- Customer records (PII)
- Payment metadata (not card numbers — those go through the payment processor)
- Application and infrastructure logs
- Backups and snapshots

## Controls verified

- Encryption at rest (KMS) on all data stores.
- Encryption in transit (TLS 1.2+) enforced.
- VPC-level isolation between environments.
- IAM reviewed quarterly (see access-reviews/).

## Sign-off

Reviewed and approved by dane@pantalasa.org on 2026-01-10.
