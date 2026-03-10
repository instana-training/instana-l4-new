# Pattern Card P10 — Automated RCA & remediation

**Module:** M4 — Integrations & Automation  
**Version:** March 2026

## Intent

Leverage Instana signals to trigger **safe automation** via the **Action Catalog** and **policies** (manual, script, HTTP, issue, Ansible). Include guardrails and auditability. [14](https://www.ibm.com/docs/en/instana-observability/current?topic=capabilities-intelligent-remediation)

## Prerequisites

- Permissions to create actions/policies; action sensors enabled on target hosts; secrets handling (vault) configured as needed. [15](https://images.g2crowd.com/uploads/attachment/file/1444513/IBM-Instana-Observability.pdf)

## Example scenario

Detect a recurring failure → run a controlled remediation (restart/feature‑flag toggle) behind a manual gate → verify outcome and record history. [14](https://www.ibm.com/docs/en/instana-observability/current?topic=capabilities-intelligent-remediation)[15](https://images.g2crowd.com/uploads/attachment/file/1444513/IBM-Instana-Observability.pdf)

## Build recipe

1. Create an **Action** (Script/HTTP/Issue/Ansible) with parameters (static/vault/dynamic). [14](https://www.ibm.com/docs/en/instana-observability/current?topic=capabilities-intelligent-remediation)
2. Define an **Automation Policy** associating the action with an event or Smart Alert; start manual, then set auto with conditions. [15](https://images.g2crowd.com/uploads/attachment/file/1444513/IBM-Instana-Observability.pdf)
3. Simulate the failure; run the action; verify KPIs and **Action History**. [15](https://images.g2crowd.com/uploads/attachment/file/1444513/IBM-Instana-Observability.pdf)

## Validation checks

- Action runs with correct inputs; policy gating works; KPIs improve post‑action; run is auditable. [15](https://images.g2crowd.com/uploads/attachment/file/1444513/IBM-Instana-Observability.pdf)

## Outputs for assessment

- 3–5 minute clip: event → recommended action → policy → run → validation (metrics/logs). [15](https://images.g2crowd.com/uploads/attachment/file/1444513/IBM-Instana-Observability.pdf)

## Top troubleshooting cues

- **Security:** require 2FA for action creation; restrict sensors to intended hosts; scrub secrets from logs. [15](https://images.g2crowd.com/uploads/attachment/file/1444513/IBM-Instana-Observability.pdf)

## Appendix

- Examples of Script vs. HTTP vs. Issue actions and tagging for “next best action”. [14](https://www.ibm.com/docs/en/instana-observability/current?topic=capabilities-intelligent-remediation)

## References (public docs)

- [Action catalog](https://www.ibm.com/docs/en/instana-observability/current?topic=capabilities-intelligent-remediation)
- [Managing actions & automation policies](https://images.g2crowd.com/uploads/attachment/file/1444513/IBM-Instana-Observability.pdf)
