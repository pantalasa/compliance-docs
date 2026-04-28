# Pantalasa Compliance Documentation

Organization-wide compliance artifacts for Pantalasa. This repository is the single source of truth for:

- Disaster recovery plan ([`docs/dr-plan.md`](docs/dr-plan.md))
- Disaster recovery exercise records ([`docs/dr-exercises/`](docs/dr-exercises/))
- Security and operational policies ([`docs/policies/`](docs/policies/))

## How it's used

Every SOC2-scoped service in the organization pulls the current state of this repository into its own Component JSON at commit time, producing a self-contained release record. The canonical collector is `compliance-bundle` (see the Lunar manifest repo).

## Contribution workflow

1. Open a PR modifying the relevant document(s).
2. A compliance reviewer approves.
3. On merge, every downstream service automatically picks up the updated compliance posture on its next commit.

## Ownership

- **Plan owner:** security@pantalasa.org
- **Exercise facilitators:** rotating, see each exercise record
- **Policy owners:** listed in each policy frontmatter

<!-- Trigger dr-docs collector under pantalasa lunar manifest -->

<!-- Trigger compliance-evidence collectors -->
<!-- re-trigger after fix -->
<!-- rerun policy-freshness -->
<!-- Trigger rerun after cataloger re-stamp -->
<!-- Trigger producer refresh (cataloger race workaround) -->
<!-- Trigger new disaster-recovery subcollector -->
