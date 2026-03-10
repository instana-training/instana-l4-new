# Pattern Card P13 — Backend deployment architectures

**Module:** M2 — Deployment & Operations  
**Version:** March 2026

## Intent

Deploy Instana backend across single-node, multi-node, and Kubernetes-based architectures; validate service health, datastore readiness, and operational baseline. 

## Prerequisites

- Linux nodes or Kubernetes cluster with appropriate compute/storage resources. 
- Network access to configure backend services, persistent storage, and certificates. 
- Instana backend installation package and `stanctl` (for single/multi-node) or Operator (for Kubernetes).
- Instana trial license (Sales Key and Download/Agent Key)

## Example scenario

Deploy a single-node Instana Standard Edition backend on a Linux VM for POC validation; or
Deploy three-node or five-node Instana Standard Edition backend ; or
Deploy a Kubernetes-based backend using the Instana Operator with persistent storage and custom CRDs. 

## Build recipe

1. **Single-node deployment:** Use `stanctl` to install on a single Linux node; configure storage, certificates, and networking; verify UI availability and datastore health. 
2. **Multi-node deployment:** Deploy across three or five nodes; assign backend, datastore, and worker roles; configure internal replication and validate failover. 
3. **Kubernetes-based backend:** Deploy Instana Operator on Kubernetes/OpenShift; define CRDs and secrets; configure persistent storage classes; validate operator readiness and backend component health. 

## Validation checks

- Backend UI accessible and responsive. 
- Datastore health confirmed (replicas, quorum status). 
- All configured nodes/pods report healthy status. 
- Internal service communication functional (backend ↔ datastore ↔ worker). 

## Outputs for assessment

- Screenshots showing backend UI service health dashboard, datastore status, and node/pod configuration for each deployment architecture. 
- 3–5 minute clip: deployment method → health validation → architectural overview. 

## Top troubleshooting cues

- **Single-node failures:** verify disk space, firewall rules, and kernel parameters configuration. 
- **Multi-node cluster issues:** confirm all nodes reachable, consistent time across nodes, and role assignments correct. 
- **Kubernetes operator issues:** check operator pod logs, CRD definitions, and persistent volume provisioning. 

## References (public docs)

- [Instana Backend Deployment Guide](https://www.ibm.com/docs/en/instana-observability)
- [Using stanctl for backend installation](https://www.ibm.com/docs/en/instana-observability)
- [Instana Operator for Kubernetes](https://www.ibm.com/docs/en/instana-observability)