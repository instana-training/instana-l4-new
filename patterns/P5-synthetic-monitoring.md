# Pattern Card P5 — Synthetic monitoring

**Module:** M3 — Digital Experience Monitoring  
**Version:** March 2026

## Intent

Configure API/Browser synthetic tests across locations; induce a failure and diagnose with waterfalls/HAR and contextual data. [9](https://github.com/instana/synthetic-synctl)

## Prerequisites

- Target URL/API; test credentials if required; permissions for Synthetic feature. [9](https://github.com/instana/synthetic-synctl)

## Example scenario

Create a browser journey and an API test; schedule in two locations; break a dependency to provoke a 5xx; review results and root cause. [9](https://github.com/instana/synthetic-synctl)

## Build recipe

1. Open **Synthetic Monitoring**; create **API** and/or **Browser** tests; set locations/schedules. [9](https://github.com/instana/synthetic-synctl)
2. Induce a controlled failure; analyze **waterfall/HAR** data and any backend context provided. [9](https://github.com/instana/synthetic-synctl)
3. (Optional) Configure **Smart Alerts** on synthetic tests. [9](https://github.com/instana/synthetic-synctl)

## Validation checks

- Test transitions **green → red** with actionable diagnostics; location impact visible. [9](https://github.com/instana/synthetic-synctl)

## Outputs for assessment

- 2–4 minute clip: config → failure → diagnosis (include waterfall/HAR references). [9](https://github.com/instana/synthetic-synctl)

## Top troubleshooting cues

- **Permissions/visibility:** ensure Synthetic Monitoring permission and PoP/location availability. [9](https://github.com/instana/synthetic-synctl)

## Appendix

- Notes on self‑hosted vs. hosted PoPs & usage considerations. [9](https://github.com/instana/synthetic-synctl)

## References (public docs)

- [Synthetic monitoring](https://github.com/instana/synthetic-synctl)
