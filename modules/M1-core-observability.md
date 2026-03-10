# Module M1 — Core Observability

**Capability goal:** Establish baseline visibility across services and infrastructure, read topology, and troubleshoot with traces, metrics, and logs. 

**Primary outcomes:** O1 (Foundations), O3 (Kubernetes & infra), O4 (Tracing), O8 (Logs & analytics), O13 (OpenTelemetry) 
---

## What you will be able to demonstrate

1. Explain the **application perspective**, service map, and health at a glance; manipulate time windows and focus queries to change analysis scope. 
2. Use **distributed tracing** + 1‑second metrics to isolate latency/error spikes and form a root‑cause hypothesis. 
3. Investigate **Kubernetes** issues from node/namespace/pod views and correlate impact to services. 
4. Ingest and query **logs**, link logs ↔ traces/metrics via **Logs in Context**, and build a minimal troubleshooting dashboard. 
5. Integrate **OpenTelemetry** (SDK or Collector/IDOT), validate TraceContext propagation, and confirm span correlation in Instana. 
---

## Pattern cards in this module

- **P1 Foundation: Observe a service end‑to‑end** (O1, O4) — discover services, diagnose a latency spike via traces & metrics. 
- **P2 Kubernetes observability** (O3) — instrument a cluster, triage a failing pod and correlate to service impact. 
- **P8 Log management & analytics** (O8) — ingest/search logs and link them with traces for faster MTTR. 
- **P11 OpenTelemetry integration** (O13) — add OTel, verify span linkage and attributes. 

---

## Prerequisites

- Access to an **Instana tenant** and a sample microservice application (or demo app). 
- Ability to deploy the **Instana agent** on a host or Kubernetes cluster (Operator/Helm/YAML). 
- Optional: familiarity with **OpenTelemetry** (OTLP exporters/collectors). 

---

## Build recipe (suggested sequence)

1. **Ensure telemetry is flowing**
   - Deploy/verify the agent (host or K8s), confirm zone naming and agent health. 
   - Open **Home → Applications/Platforms/Infrastructure** and verify discovered services. 
2. **Trace-led triage**
   - Use **Analytics → Traces** to filter by latency/errors and open a waterfall to locate the bottleneck. 
3. **Kubernetes correlation**
   - From **Platforms/Kubernetes**, find a CrashLoopBackOff (or simulate), link to the affected service and show impact. 
4. **Logs in Context**
   - Send logs, build a focused query, and link a log line to a trace. Save a simple dashboard panel. 
5. **OpenTelemetry validation**
   - Configure OTel SDK/Collector (IDOT), generate load, and confirm spans appear under the right services with intact parent/child links. 
---

## Completion evidence

- **Video** (8–12 min or 2–3 shorter clips) showing:
  - Service discovery & application perspective;
  - A trace‑based RCA walk‑through;
  - One K8s incident correlation;
  - Logs query linked to a trace;
  - OTel span correlation proof (screenshot or short demo). 

---

## References (public docs)

- [About Instana (overview)](https://www.ibm.com/docs/en/instana-observability/1.0.315?topic=overview) · 
- [Working with the Instana UI](https://www.ibm.com/docs/en/instana-observability/1.0.315?topic=working-user-interface)
- [Installing Instana agents](https://www.ibm.com/docs/en/instana-observability/1.0.315?topic=installing-instana-agents) · 
- [Logging (overview)](https://www.ibm.com/docs/en/instana-observability/1.0.315?topic=instana-logging) · 
- [Analyzing logs](https://github.com/instana/go-sensor)
- [OpenTelemetry with Instana](https://github.com/instana/instana-otel-collector)
