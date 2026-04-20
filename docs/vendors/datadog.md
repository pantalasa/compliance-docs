---
vendor: "Datadog"
category: "observability"
last_assessed: "2025-11-18"
next_review: "2026-11-18"
soc2_on_file: true
soc2_report_date: "2025-06-30"
data_classification: "internal"
criticality: "tier-2"
reviewer: "mick@pantalasa.org"
---

# Vendor Assessment — Datadog

## Summary

Datadog provides our APM, logging, and alerting pipeline for production services. Application logs and metrics are shipped to Datadog's US1 region.

## Assessment

| Field | Value |
|-------|-------|
| Last assessed | 2025-11-18 |
| Next review | 2026-11-18 (annual) |
| SOC 2 on file | yes (Type II, report dated 2025-06-30) |
| ISO 27001 on file | yes |
| Data classification | internal |
| Criticality | tier-2 |
| MSA in place | yes |
| DPA in place | yes |

## Data processed

- Application logs (redacted — no PII fields, no payment data).
- Performance and error metrics.
- Custom business-metric time series.

## Controls verified

- Log redaction is applied at the client library before send; verified via sampling.
- Datadog-side retention configured at 30 days for logs, 15 months for metrics.
- Account-level SSO with SCIM provisioning.

## Sign-off

Reviewed and approved by mick@pantalasa.org on 2025-11-18.
