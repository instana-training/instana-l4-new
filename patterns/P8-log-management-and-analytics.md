# Pattern Card P8 — Log management & analytics

**Module:** M1 — Core Observability  
**Version:** March 2026

## Intent

Ingest and query logs, correlate with traces/metrics via **Logs in Context**, and create a minimal dashboard or saved query for recurring analysis. [5](https://ibm-bp-tech.github.io/Instana-1-Day-Partner-Workshop/Labs/Lab2/)

## Prerequisites

- Log shipper/agent configured (native or via OpenTelemetry); appropriate permissions for log views. [5](https://ibm-bp-tech.github.io/Instana-1-Day-Partner-Workshop/Labs/Lab2/)

## Example scenario

Ship application logs; build a focused query (filters/groups/regex); correlate a log outlier to a bad deployment traced earlier; save a panel. [6](https://github.com/instana/go-sensor)

## Build recipe

1. Configure log ingestion path and verify **Logs** summary. [5](https://ibm-bp-tech.github.io/Instana-1-Day-Partner-Workshop/Labs/Lab2/)
2. Use **Analytics → Logs**: add filters/groups; test a regex if useful; pivot to traces. [6](https://github.com/instana/go-sensor)
3. Create a **saved query** or dashboard panel to monitor the pattern. [5](https://ibm-bp-tech.github.io/Instana-1-Day-Partner-Workshop/Labs/Lab2/)

## Validation checks

- Logs searchable; pivot to a related trace shows the connection; panel/query saved. [6](https://github.com/instana/go-sensor)

## Outputs for assessment

- 2–3 minute clip: query construction → correlation → dashboard/panel. [6](https://github.com/instana/go-sensor)

## Top troubleshooting cues

- **Volume/retention limits:** check add‑on activation and permissions for log retention/volume views. [5](https://ibm-bp-tech.github.io/Instana-1-Day-Partner-Workshop/Labs/Lab2/)

## Appendix

- Field naming conventions and tagging tips. [5](https://ibm-bp-tech.github.io/Instana-1-Day-Partner-Workshop/Labs/Lab2/)

## References (public docs)

- [Logging (overview)](https://ibm-bp-tech.github.io/Instana-1-Day-Partner-Workshop/Labs/Lab2/)
- [Analyzing logs](https://github.com/instana/go-sensor)
  ``
