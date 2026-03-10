# Pattern Card P2 — Kubernetes observability

**Module:** M1 — Core Observability  
**Version:** March 2026

## Intent

Instrument a K8s cluster and troubleshoot a pod failure with correlated service impact using Instana’s Kubernetes view and trace/log links. [3](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=actions-action-catalog)

## Prerequisites

- Cluster admin access to deploy Instana agent via **Operator** or **Helm**. [3](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=actions-action-catalog)
- Ability to simulate a failing Pod (e.g., CrashLoopBackOff). [3](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=actions-action-catalog)

## Example scenario

Deploy the agent with Helm, confirm namespace discovery, trigger a failing deployment, then use K8s view → service map → related traces/logs to assess impact. [3](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=actions-action-catalog)

## Build recipe

1. **Install agent** using **Helm v2.x** (installs operator & CRD) or Operator; set `zone/cluster` identifiers. [4](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=instana-synthetic-monitoring)
2. Validate **cluster/namespace** visibility and node coverage in Instana. [3](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=actions-action-catalog)
3. Introduce a pod failure; open **Platforms → Kubernetes** to locate the failing pod and linked services. [3](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=actions-action-catalog)
4. Open related **traces/logs** to corroborate user‑visible impact. [5](https://ibm-bp-tech.github.io/Instana-1-Day-Partner-Workshop/Labs/Lab2/)[6](https://github.com/instana/go-sensor)

## Validation checks

- Cluster and namespaces visible; failing pod identified. [3](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=actions-action-catalog)
- Evidence linking pod condition to service KPI degradation using traces/logs. [5](https://ibm-bp-tech.github.io/Instana-1-Day-Partner-Workshop/Labs/Lab2/)[6](https://github.com/instana/go-sensor)

## Outputs for assessment

- 3–5 minute clip: install method & config → failure → correlated impact story. [4](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=instana-synthetic-monitoring)

## Top troubleshooting cues

- **DaemonSet not scheduling / operator issues:** verify permissions/tolerations and egress to Instana backend. [3](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=actions-action-catalog)
- **Missing namespaces:** confirm label/namespace filters and CR values. [4](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=instana-synthetic-monitoring)

## Appendix

- Minimal Helm values (redacted) & Operator CR examples. [4](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=instana-synthetic-monitoring)

## References (public docs)

- [Installing the agent on Kubernetes](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=actions-action-catalog)
- [Instana Agent Helm chart (Artifact Hub)](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=instana-synthetic-monitoring)
  ``
