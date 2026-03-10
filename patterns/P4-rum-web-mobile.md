# Pattern Card P4 — RUM for Web & Mobile

**Module:** M3 — Digital Experience Monitoring  
**Version:** March 2026

## Intent

Instrument Real User Monitoring (RUM) and analyze **Session Replay** for a failing journey; link frontend signals to backend traces. [8](https://registry.terraform.io/providers/instana/instana/latest/docs/resources/rbac_role)

## Prerequisites

- Access to a web or mobile app to inject RUM snippet/SDK; permission to collect replay data. [8](https://registry.terraform.io/providers/instana/instana/latest/docs/resources/rbac_role)

## Example scenario

Enable RUM on a test site; capture sessions; identify high JS errors, then pivot from replay to a backend trace explaining the incident. [8](https://registry.terraform.io/providers/instana/instana/latest/docs/resources/rbac_role)

## Build recipe

1. Open **Websites & Mobile Apps** → add site/app; install the RUM snippet/SDK per UI guidance. [8](https://registry.terraform.io/providers/instana/instana/latest/docs/resources/rbac_role)
2. Validate **beacons** and review RUM dashboards (page loads, JS errors). [8](https://registry.terraform.io/providers/instana/instana/latest/docs/resources/rbac_role)
3. Open **Session Replay** and use correlation to reach the backend trace for the failing path. [8](https://registry.terraform.io/providers/instana/instana/latest/docs/resources/rbac_role)

## Validation checks

- RUM data present; a replay session links to a backend trace. [8](https://registry.terraform.io/providers/instana/instana/latest/docs/resources/rbac_role)

## Outputs for assessment

- 3–4 minute clip: RUM install → dashboard signals → replay → backend trace. [8](https://registry.terraform.io/providers/instana/instana/latest/docs/resources/rbac_role)

## Top troubleshooting cues

- **No data/replay:** confirm CSP/allow‑list and that tracking snippet is active; verify correlation headers. [8](https://registry.terraform.io/providers/instana/instana/latest/docs/resources/rbac_role)

## Appendix

- Notes on SPA auto‑transition detection and SRI option. [8](https://registry.terraform.io/providers/instana/instana/latest/docs/resources/rbac_role)

## References (public docs)

- [Monitoring websites (RUM)](https://registry.terraform.io/providers/instana/instana/latest/docs/resources/rbac_role)
  ``
