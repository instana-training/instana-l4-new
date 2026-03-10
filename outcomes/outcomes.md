# Outcomes (Badge Contract) — IBM Instana Level 4

This page defines the **durable, UI‑independent outcomes** that the Instana L4 badge certifies.  
They are grouped into capability **modules** and include the **evidence** a learner must demonstrate on video (single 8–12 min video **or** 2–3 shorter clips).

> These outcomes rely on public IBM Instana documentation and product references so they remain valid across UI changes.

---

## Contents

1. [Philosophy & Assessment](#philosophy--assessment)
2. [Outcome-to-Module Map](#outcome-to-module-map)
3. [Outcomes (O1–O14)](#outcomes-o1o14)
4. [Evidence Guide (what “done” looks like)](#evidence-guide-what-done-looks-like)
5. [Dependencies & Prerequisites](#dependencies--prerequisites)

---

## Philosophy & Assessment

- **Outcomes are durable:** they certify what you can do with Instana (capability), not where to click (procedures).
- **Assessment is practical:** show an observable build and reasoning that would satisfy a technical manager.
- **Submission:** one **8–12 minute** video, or **2–3 shorter** clips that together prove all selected outcomes for your path.
- **Primary evidence types:**
  - Service topology, traces, metrics, dashboards (UI walkthrough)  
  - K8s/agent lifecycle and GitOps artifacts (values/CRD/operator) 
  - API/OTel integrations and automation actions (Action Catalog) 

---

## Outcome-to-Module Map

| Module                               | Capability Theme                                                            | Outcomes                                                                                                                                                                                                                                                                                    |
| ------------------------------------ | --------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **M1 Core Observability**            | Discover services, analyze traces/metrics/logs, K8s views, OTel correlation | **O1, O3, O4, O8, O13**  |
| **M2 Deployment & Operations**       | Install/manage agents, CI/CD & GitOps, alerts/SLOs                          | **O2, O5, O10**  |
| **M3 Digital Experience Monitoring** | Real User Monitoring, Session Replay, Synthetic                             | **O6, 07**       |
| **M4 Integrations & Automation**     | REST/OpenAPI, automation policies, action catalog                           | **O9, O12**      |
| **M5 Security & Governance**         | RBAC/SSO, audit, usage & billing, FinOps views                              | **O11, O14**     |


---

## Outcomes (O1–O14)

### O1. Core Observability Foundations

Demonstrate navigation of **service maps**, **application perspectives**, and **analytics** to explain a system’s structure and health at a glance. Show how time windows and focus queries change the analysis scope. 

**Evidence:** Walkthrough of the topology and an application perspective, explaining a suspected issue path and relevant KPIs.

---

### O2. Agent Deployment & Lifecycle

Install and validate the **Instana agent** on Linux/hosts or **Kubernetes**; explain update strategy (Operator/Helm CRDs), zone naming, and health signals. Show where to verify agent state and logs. 

**Evidence:** Fresh install (or controlled upgrade), health validation, and reasoning for Helm vs. Operator in your environment.

---

### O3. Kubernetes & Infrastructure Monitoring

Use the K8s view to correlate **node/namespace/pod** conditions with service impact; identify a failing pod and link to traces/logs. Explain DaemonSet/operator behaviors and network egress prerequisites at a high level. 

**Evidence:** CrashLoopBackOff (or similar) triage with correlated infra → service evidence.

---

### O4. Application Performance & Distributed Tracing

Isolate a **latency** or **error** spike using trace waterfalls, service/end‑point analytics, and infrastructure context. Explain how 1‑second metrics and every‑trace capture support RCA. 

**Evidence:** Before/after metrics panel + a trace that pinpoints a bottleneck (e.g., DB call).

---

### O5. Events, Smart Alerts & SLOs

Create **SLOs** (SLI, target, error budget) and configure **Smart Alerts** (status, budget %, **burn‑rate** with long/short windows). Show alert routing and noise‑reduction choices. 

**Evidence:** Fired alert with context and an explanation of thresholds vs. sensitivity.

---

### O6. Digital Experience Monitoring (RUM / Session Replay)

Instrument web (and/or mobile) **RUM** to capture page loads and **Session Replay**, linking front‑end signals to backend traces. Explain beaconing and SPA auto‑transitions at a high level. 

**Evidence:** A replayed session that correlates to a backend trace for a poor user experience.

---

### O7. Synthetic Monitoring

Create **API** and/or **browser** synthetic tests, schedule them across locations, and triage a failure (waterfall, HAR/network, backend correlation). Describe when synthetics complement RUM and SLOs. 

**Evidence:** Test turns **green → red** with a diagnosis and improvement step.

---

### O8. Logs & Analytics

Ingest and analyze **logs**; build a focused query (grouping, filters, regex if needed) and link logs with traces/metrics (**Logs in Context**). Show dashboarding or saved queries. 

**Evidence:** Troubleshooting sequence where a log pattern explains a spike seen in traces/metrics.

---

### O9. Integrations & APIs

Call **Instana REST APIs** (auth token, endpoints, pagination/rate limits), or integrate with external systems (e.g., webhooks/BI). Explain token scopes and error handling. Optionally reference the public OpenAPI spec. 

**Evidence:** One successful API workflow plus one controlled failure (401/429) with fix.

---

### O10. CI/CD & GitOps for Instana Configuration

Manage agent/config as code (Helm values, Operator CRs), promote changes across environments and detect **drift**. Explain rollback strategy. 

**Evidence:** PR → pipeline run → rollout → validation; show a safe rollback path.

---

### O11. Security & Governance (RBAC, SSO/MFA, Audit)

Configure **RBAC** roles/teams and **SSO/MFA**; explain least‑privilege and scope‑limited access for apps, K8s, logs, DEM, synthetics. Point to audit/usage views. 

**Evidence:** Role definitions tied to a scoped resource set + a working SSO login path.

---

### O12. Automated RCA & Remediation (Action Catalog)

Use **Action Catalog** and **automation policies** to create safe, auditable remediation (manual/HTTP/script/Ansible), with parameters and approvals. Explain security considerations. 

**Evidence:** Recommended action attached to an event; show policy run and outcome evidence.

---

### O13. OpenTelemetry Integration

Instrument an app with **OpenTelemetry** (SDK or Collector/IDOT), ensure **TraceContext** propagation, and verify **span correlation** and attributes in Instana. Clarify the move to **OTLP** exporters. 

**Evidence:** Code/config snippet → traffic → trace groups with correct parent/child relationships and service naming.

---

### O14. Cost Insights / FinOps (Usage, Efficiency Views)

Use Instana’s **native integration with IBM Kubecost** to bring **Kubernetes cost, allocation, efficiency, and savings metrics** directly into the Instana console.  
Correlate cost spikes with deployments, performance regressions, namespace‑level activity, and cluster utilization trends to drive **FinOps‑aligned optimization**.  

**Evidence:** Configuration of Instana host agent to ingest Kubecost data. Use Cost related dashboards to identify top cost genrating namespaces and deployments.



---

## Evidence Guide (what “done” looks like)

Each module submission should include:

- **One success path + one induced failure** with reasoning steps (where applicable).
- **Where in Instana** the proof comes from (topology, analytics, logs, DEM, synthetics, actions). 
- **Trade‑offs & guardrails** (e.g., alert sensitivity vs. noise; GitOps rollback; automation approvals). 

---

## Dependencies & Prerequisites

- **O1** is foundational for all other outcomes (you need to read the environment context). 
- **O2 → O3/O4/O8/O13:** solid agent/K8s setup before deep analysis, logging, or OTel correlation. 
- **O5** benefits from **O4** (stable SLI signals) and may feed **O12** (policy triggers). 
- **O6/O7** can be pursued independently but correlate well with **O4** for end‑to‑end journeys. 
- **O9/O10** underpin repeatability, exports, and integrations used by **O12**. 
- **O11/O14** are cross‑cutting governance and efficiency layers for all modules. 

---

## Appendix: Quick Links (Public Docs)

- Overview & UI: [About Instana] and [Working with the UI] 
- Agents/K8s: [Kubernetes agent install](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=kubernetes-installing-agent), [Agent Helm chart](https://github.com/instana/helm-charts)
- Agents/Host: [Linux agent install](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=linux-installing-agent). [Windows agent install](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=agents-installing-windows)
- Agents/Cloud services [Cloud service agent install](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=agents-installing-configuring-cloud-service)
- DEM: [Monitoring websites (RUM)](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=instana-monitoring-websites#installation), [Synthetic monitoring](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=instana-synthetic-monitoring)
- Logging: [Logging](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=instana-logging), [Analyzing logs](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=logging-analyzing-logs)
- API/Integrations: [REST API getting started](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=sdks-getting-started-instana-rest-api), [OpenAPI spec](https://developer.ibm.com/apis/catalog/instana--instana-rest-api/Introduction)
- OTel: [OpenTelemetry with Instana](https://github.com/instana/instana-otel-collector)
- Automation: [Action catalog], [Intelligent remediation](https://www.ibm.com/docs/en/instana-observability/current?topic=capabilities-intelligent-remediation)
- Security [Configuring authentication](https://www.ibm.com/docs/en/instana-observability/1.0.312?topic=instana-configuring-authentication)
