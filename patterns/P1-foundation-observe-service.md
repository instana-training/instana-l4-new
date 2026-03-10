# Pattern Card P1 — Foundation: Observe a service end-to-end

**Module:** M1 — Core Observability  
**Version:** March 2026

## Intent

Discover services, visualize dependencies, and diagnose a latency spike using distributed tracing and 1‑second metrics to form a root‑cause hypothesis. [1](https://www.postman.com/interstellar-space-351769/instana-public-api/collection/q3i8imp/introduction-to-instana-public-apis)

## Prerequisites

- Access to an Instana tenant with a running application perspective visible in the UI. [2](https://ibm.github.io/aiops-pot/docs/Instana%20POT/Monitoring%20a%20Cloud%20Native%20App/agent-install/)
- Basic traffic hitting the service under observation (dev/staging is fine). [1](https://www.postman.com/interstellar-space-351769/instana-public-api/collection/q3i8imp/introduction-to-instana-public-apis)

## Example scenario

Use a demo “checkout” service generating traffic; investigate a sudden p95 latency increase by navigating from the **application perspective** to **trace waterfalls** and correlated infrastructure panels. [2](https://ibm.github.io/aiops-pot/docs/Instana%20POT/Monitoring%20a%20Cloud%20Native%20App/agent-install/)[1](https://www.postman.com/interstellar-space-351769/instana-public-api/collection/q3i8imp/introduction-to-instana-public-apis)

## Build recipe

1. Open **Applications → [your application]** and review the **service map** and KPIs (error %, latency, throughput). Adjust time window if needed. [2](https://ibm.github.io/aiops-pot/docs/Instana%20POT/Monitoring%20a%20Cloud%20Native%20App/agent-install/)
2. From the service or endpoint, jump to **Analytics → Traces** and filter by high latency/failed calls; open a trace and read the **waterfall**. [2](https://ibm.github.io/aiops-pot/docs/Instana%20POT/Monitoring%20a%20Cloud%20Native%20App/agent-install/)
3. Inspect suspect spans (e.g., DB call) and correlate with host/container metrics at that time. [1](https://www.postman.com/interstellar-space-351769/instana-public-api/collection/q3i8imp/introduction-to-instana-public-apis)
4. Capture before/after metrics (optional: apply a config change), then re‑run traffic to validate. [1](https://www.postman.com/interstellar-space-351769/instana-public-api/collection/q3i8imp/introduction-to-instana-public-apis)

## Validation checks (what “done” looks like)

- Service visible in the **map** with correct dependencies. [2](https://ibm.github.io/aiops-pot/docs/Instana%20POT/Monitoring%20a%20Cloud%20Native%20App/agent-install/)
- At least one trace shows the **bottleneck** span with supporting metrics. [1](https://www.postman.com/interstellar-space-351769/instana-public-api/collection/q3i8imp/introduction-to-instana-public-apis)
- A short explanation of likely root cause grounded in evidence. [1](https://www.postman.com/interstellar-space-351769/instana-public-api/collection/q3i8imp/introduction-to-instana-public-apis)

## Outputs for assessment

- 2–4 minute clip walking map → trace → bottleneck callout. Include a screenshot of the service map and the trace waterfall. [2](https://ibm.github.io/aiops-pot/docs/Instana%20POT/Monitoring%20a%20Cloud%20Native%20App/agent-install/)

## Top troubleshooting cues

- **No services discovered:** verify agents and supported tech instrumentation are active. [1](https://www.postman.com/interstellar-space-351769/instana-public-api/collection/q3i8imp/introduction-to-instana-public-apis)
- **Trace gaps:** check sampling/filters and app connectivity to Instana backend. [1](https://www.postman.com/interstellar-space-351769/instana-public-api/collection/q3i8imp/introduction-to-instana-public-apis)

## Appendix — Recommended text blocks

- **Observation checklist:** time window set, focus query applied, KPI deltas called out. [2](https://ibm.github.io/aiops-pot/docs/Instana%20POT/Monitoring%20a%20Cloud%20Native%20App/agent-install/)

## References (public docs)

- [About Instana (overview)](https://www.postman.com/interstellar-space-351769/instana-public-api/collection/q3i8imp/introduction-to-instana-public-apis)
- [Working with the Instana UI](https://ibm.github.io/aiops-pot/docs/Instana%20POT/Monitoring%20a%20Cloud%20Native%20App/agent-install/)
