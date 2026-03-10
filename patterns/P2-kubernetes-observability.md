# Pattern Card P2 — Kubernetes observability

- **Module:** M1 — Core Observability  
- **Version:** March 2026

## Intent

Instrument a K8s cluster and troubleshoot a pod failure with correlated service impact using Instana’s Kubernetes view and trace/log links. 

## Prerequisites

- Cluster admin access to deploy Instana agent via **Operator** or **Helm**. 
- Ability to simulate a failing Pod (e.g., CrashLoopBackOff). 

## Example scenario

Deploy the agent with Helm, confirm namespace discovery, trigger a failing deployment, then use K8s view → service map → related traces/logs to assess impact. 

## Build recipe

1. **Install agent** using **Helm v2.x** (installs operator & CRD) or Operator; set `zone/cluster` identifiers. 
2. Validate **cluster/namespace** visibility and node coverage in Instana. 
3. Introduce a pod failure; open **Platforms → Kubernetes** to locate the failing pod and linked services. 
4. Open related **traces/logs** to corroborate user‑visible impact. 

## Validation checks

- Cluster and namespaces visible; failing pod identified. 
- Evidence linking pod condition to service KPI degradation using traces/logs. 

## Outputs for assessment

- 3–5 minute clip: install method & config → failure → correlated impact story. 

## Top troubleshooting cues

- **DaemonSet not scheduling / operator issues:** verify permissions/tolerations and egress to Instana backend. 
- **Missing namespaces:** confirm label/namespace filters and CR values. 

## Related hands-on labs

- L1 Agent installation

## Related pattern cards

- P12 Cost Insights and FinOps
- P8 Log mamangement and analytics


## References (public docs)

- [Installing the agent on Kubernetes](https://www.ibm.com/docs/en/instana-observability/1.0.315?topic=agents-installing-kubernetes)
- [Monitoring Kubernetes](https://www.ibm.com/docs/en/instana-observability/1.0.315?topic=instana-monitoring-kubernetes)

