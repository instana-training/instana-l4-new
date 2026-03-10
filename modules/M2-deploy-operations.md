# Module M2 — Deployment & Operations

**Capability goal:** Deploy and manage complete Instana backend deployments across multiple architectures and manage Instana agents and configuration reliably across environments (host agents, Kubernetes agents, and cloud service agents); implement actionable alerting and SLOs; operationalize GitOps/CI‑CD for Instana following IBM Instana best practices and official documentation.

**Primary outcomes:** O2 (Agent lifecycle), O5 (Smart alerts & SLOs), O10 (CI/CD & GitOps), O11 (Backend deployment), O12 (Backend operations), O13 (Cloud service agents)

---

## What you will be able to demonstrate

1. Deploy Instana **backend** in multiple supported architectures (single-node, multi-node, Kubernetes-based) and validate service health. 
2. Install and manage **host, Kubernetes, and cloud service agents** and verify end-to-end data ingestion. 
3. Choose and justify an **agent deployment** method (Operator/Helm/YAML) and verify health/coverage.
4. Configure **SLOs** (SLI/targets/error budgets) and **Smart Alerts** with burn‑rate windows and routing.
5. Manage Instana configuration as code (values/CRDs), promote changes between **dev → stage** with **GitOps/CI‑CD**, detect and resolve **drift**, and perform a rollback.

---

## Pattern cards in this module

- **P13 Backend deployment architectures** (O11) — deploy single-node, multi-node, and Kubernetes-based backends; configure storage, certificates, and networking. 
- **P14 Backend operations & Day-2** (O12) — validate health, manage upgrades, scale components, and troubleshoot. 
- **P15 Cloud service agent integration** (O13) — configure cloud monitoring for AWS/Azure/GCP; enable integrations and validate ingestion. 
- **P3 Smart alerts & SLOs** (O5) — design SLOs, set blueprints, trigger and triage alerts. 
- **P7 CI/CD & GitOps for agent management** (O2, O10) — pipeline‑driven rollout, validation, and rollback. 

---

## Prerequisites

- Access to **Linux nodes or Kubernetes cluster** for backend and agent deployment; **CI system and Git repository**. 
- Cloud provider accounts (AWS/Azure/GCP) with appropriate IAM/service principal permissions for cloud integrations. 
- For agent management: Instana tenant with permissions to configure **alerts/SLOs**, **agent settings**, and **backend components**. 

---

## Build recipe (suggested sequence)

### 1. Backend deployment and validation

#### 1a. Single-node backend (Standard Edition)
- Deploy Instana backend on a single Linux node using `stanctl`.
- Configure required storage, certificates, authentication, and networking.
- Validate UI availability, datastore health, and service readiness.
- Document limitations and suitable use cases (POC, non-production). 

#### 1b. Multi-node backend (Standard Edition) (three or five nodes)
- Deploy a multi-node Instana backend cluster across three or five nodes.
- Assign backend, datastore, and worker roles across nodes.
- Configure internal communication and data replication.
- Validate high availability of core backend services and failover behavior. 

#### 1c. Kubernetes-based backend deployment (Custom Edition)
- Deploy Instana backend using the Instana Operator on Kubernetes or OpenShift.
- Configure Custom Resource Definitions (CRDs), secrets, and certificates.
- Configure persistent storage using supported storage classes.
- Validate backend components, operators, and upgrade readiness. 

**Evidence:** Screenshots showing backend UI service health, datastore status, and configured nodes.

### 2. Host and Kubernetes agent deployment

#### 2a. Host agent rollout
- Install Instana host agent on Linux systems.
- Configure agent keys, endpoint URLs, proxy settings, zones, tags, and metadata.
- Validate infrastructure and process visibility. 

#### 2b. Kubernetes agent rollout with Helm or Operator
- Install via **Helm chart** (v2.x deploys an operator + CRD) and set `zone/cluster` identifiers.
- Configure cluster name, namespaces, and RBAC permissions.
- Validate agent scheduling, health, pod discovery, and container metrics. 

**Evidence:** Screenshots showing agent status, monitored entities, and data flow in Instana UI.

### 3. Cloud service agent integration

- Configure cloud monitoring for supported providers (AWS, Azure, GCP).
- Enable cloud integrations using IAM roles, service principals, or API keys.
- Assign zones, tags, and account-level organization.
- Validate ingestion of cloud services (load balancers, databases, messaging). 

**Evidence:** Screenshots showing cloud service entities and metrics in Instana UI.

### 4. GitOps pipeline for agent and backend configuration

- Store Helm values, CRDs, and deployment manifests in Git.
- Open PR for environment promotion (dev → stage).
- Pipeline applies manifests and validates drift and health dashboards.
- Document rollback steps and perform a controlled rollback. 

**Evidence:** Screenshots or recording of PR, pipeline execution, and post-deployment validation.

### 5. Backend operations and Day-2 management

- Perform backend upgrades using supported upgrade paths.
- Scale backend and agent components safely.
- Validate post-upgrade system health and data continuity.
- Configure alerts and SLOs for operational readiness. 

**Evidence:** Screenshots showing upgrade status, scaling operations, and health dashboards.

### 6. SLOs and Smart Alerts

- Define SLIs/targets and configure **error budget**, **status**, or **burn‑rate** alerts.
- Attach notification channels (e.g., webhook).
- Trigger a controlled SLO breach and show the alert context and action taken. 

**Evidence:** Screenshots or recording of SLO config, fired Smart Alert, and remediation.

---

## Completion evidence

- **Video** (12–15 min or 3–4 shorter clips) covering:
  - Backend deployment (single-node or multi-node) with service health verification;
  - Host and Kubernetes agent rollout with data validation;
  - Cloud service integration setup;
  - PR‑driven promotion and configuration validation;
  - A backend upgrade or scaling operation;
  - An SLO and a fired Smart Alert with the action taken. 

Alternatively, **comprehensive screenshots** demonstrating each section above with annotations explaining the setup and validation steps.

---

## References (public docs)

- [Instana Backend Deployment Guide](https://www.ibm.com/docs/) · [stanctl Documentation](https://www.ibm.com/docs/)
- [Installing the agent on Kubernetes](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=actions-action-catalog) · [Instana Agent Helm chart](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=instana-synthetic-monitoring)
- [Cloud Service Agent Configuration](https://www.ibm.com/docs/) · [AWS/Azure/GCP Integration](https://www.ibm.com/docs/)
- [Smart Alerts for Service Level Objectives](https://b1stern.github.io/InstanaMiddlewareLab/tutorials/Administration/)
- [Configuration-as-Code for Instana](https://www.ibm.com/docs/)
