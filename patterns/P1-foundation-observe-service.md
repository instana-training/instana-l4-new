# Pattern Card P1 — Foundation: Observe a service end-to-end

- **Module:** M1 — Core Observability  
- **Version:** March 2026

## Intent

Discover services, visualize dependencies, and diagnose a latency spike using distributed tracing and 1‑second metrics to form a root‑cause hypothesis. 

## Prerequisites

- Access to an Instana tenant with a running application perspective visible in the UI. 
- Demo Apps deployed to the target environment
- Instana agent deployed to the target environment
- Basic traffic hitting the service under observation (dev/staging is fine). 

## Example scenario

Use a demo application from demo-apps, for example “checkout” service while generating traffic; investigate a sudden p95 latency increase by navigating from the **application perspective** to **trace waterfalls** and correlated infrastructure panels. 

## Build recipe

1. Open **Applications → [your application]** and review the **service map** and KPIs (error %, latency, throughput). Adjust time window if needed. 
2. From the service or endpoint, jump to **Analytics → Traces** and filter by high latency/failed calls; open a trace and read the **waterfall**. 
3. Inspect suspect spans (e.g., DB call) and correlate with host/container metrics at that time. 
4. Capture before/after metrics (optional: apply a config change), then re‑run traffic to validate. 

## Validation checks (what “done” looks like)

- Service visible in the **map** with correct dependencies. 
- At least one trace shows the **bottleneck** span with supporting metrics. 
- A short explanation of likely root cause grounded in evidence. 

## Outputs for assessment

- 2–4 minute clip walking map → trace → bottleneck callout. Include a screenshot of the service map and the trace waterfall. 

## Hands-on Lab refereces

- L4 Explore Demo App
- L6 Application Perspectives
- L7 Serice Mapping
- L8 Endpoint Mapping

## Top troubleshooting cues

- **No services discovered:** verify agents and supported tech instrumentation are active. 
- **Trace gaps:** check sampling/filters and app connectivity to Instana backend. 

## References (public docs)

- [About Instana (overview)](https://www.ibm.com/docs/en/instana-observability/1.0.315?topic=overview)
- [Working with the Instana UI](https://www.ibm.com/docs/en/instana-observability/1.0.315?topic=instana-monitoring-applications)
- [Analyzing traces and calls](https://www.ibm.com/docs/en/instana-observability/1.0.315?topic=applications-analyzing-traces-calls)
