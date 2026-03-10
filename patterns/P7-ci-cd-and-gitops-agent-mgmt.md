# Pattern Card P7 — CI/CD & GitOps for agent management

**Module:** M2 — Deployment & Operations  
**Version:** March 2026

## Intent

Manage Instana agent deployment/configuration as code; promote safely across environments with CI/CD, detect drift, and rollback. [4](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=instana-synthetic-monitoring)

## Prerequisites

- Git repository & CI pipeline; K8s or hosts where agents are installed. [4](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=instana-synthetic-monitoring)

## Example scenario

Define Helm values/Operator CRs in Git; open PR to promote from dev → stage; pipeline applies changes; validate agent health; demonstrate rollback. [4](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=instana-synthetic-monitoring)

## Build recipe

1. Create or update **values.yaml** (or CR) with zone/cluster and backend endpoints. [4](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=instana-synthetic-monitoring)
2. Pipeline applies to **dev** on merge; health verification gates promotion. [4](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=instana-synthetic-monitoring)
3. PR → **stage**; apply; check **Agents/health** dashboards; note any **drift** and reconcile. [4](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=instana-synthetic-monitoring)
4. Document and test a **rollback** path. [4](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=instana-synthetic-monitoring)

## Validation checks

- Successful promotion with agent health green; documented rollback works. [4](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=instana-synthetic-monitoring)

## Outputs for assessment

- 3–5 minute clip: PR → pipeline run → validation; diff of values/CRs; rollback demo. [4](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=instana-synthetic-monitoring)

## Top troubleshooting cues

- **CRD/order issues:** remember Helm + operator/CRD lifecycle; check RBAC. [4](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=instana-synthetic-monitoring)

## Appendix

- Example values/CR snippets (redacted secrets). [4](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=instana-synthetic-monitoring)

## References (public docs)

- [Instana Agent Helm chart (Artifact Hub)](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=instana-synthetic-monitoring)
- [Instana Agent Operator (GitHub)](https://catalog.redhat.com/en/software/containers/instana/instana-agent-operator-bundle/5f60f463ac3db90370a1d070)
