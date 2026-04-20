---
vendor: "Stripe"
category: "payment-processor"
last_assessed: "2025-12-05"
next_review: "2026-12-05"
soc2_on_file: true
soc2_report_date: "2025-10-15"
pci_dss_on_file: true
data_classification: "restricted"
criticality: "tier-1"
reviewer: "dane@pantalasa.org"
---

# Vendor Assessment — Stripe

## Summary

Stripe is our payment processor. Card numbers are never handled by our services — we use Stripe Elements and Checkout so all cardholder data goes directly to Stripe. We store only payment method tokens and transaction metadata.

## Assessment

| Field | Value |
|-------|-------|
| Last assessed | 2025-12-05 |
| Next review | 2026-12-05 (annual) |
| SOC 2 on file | yes (Type II, report dated 2025-10-15) |
| PCI DSS on file | yes (Level 1 Service Provider) |
| Data classification | restricted |
| Criticality | tier-1 |
| MSA in place | yes |
| DPA in place | yes |

## Data processed

- Customer email addresses (for receipts).
- Payment method tokens (Stripe-issued, non-sensitive).
- Transaction metadata (amounts, currencies, timestamps).

## Controls verified

- Card data never transits our infrastructure; verified by code review of client integration.
- Stripe webhooks signed and verified by our receiver.
- Scoped API keys per environment; rotation in last 90 days confirmed.

## Sign-off

Reviewed and approved by dane@pantalasa.org on 2025-12-05.
