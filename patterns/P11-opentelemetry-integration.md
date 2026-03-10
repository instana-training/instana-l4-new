# Pattern Card P11 — OpenTelemetry integration

**Module:** M1 — Core Observability (cross‑cutting)  
**Version:** March 2026

## Intent

Instrument an application with OpenTelemetry (SDK or Collector/IDOT), ensure **W3C TraceContext** propagation, and validate correlation with Instana services and traces. [16](https://github.com/instana/instana-otel-collector)

## Prerequisites

- Sample service where you can add an OTel SDK or route via the **Instana Distribution of the OpenTelemetry Collector (IDOT)**. [17](https://www.linkedin.com/pulse/streaming-out-instana-signalsmetricstraceslogs-through-madhu-bhangi-svsfc)

## Example scenario

Add OTel SDK to a service, export spans/metrics via OTLP to the Instana agent or backend (IDOT), generate traffic, confirm correct service naming and parent/child relationships. [16](https://github.com/instana/instana-otel-collector)

## Build recipe

1. Configure OTel SDK/Collector with Instana OTLP endpoints (IDOT simplifies setup) and resource attributes (service name). [17](https://www.linkedin.com/pulse/streaming-out-instana-signalsmetricstraceslogs-through-madhu-bhangi-svsfc)
2. Ensure **TraceContext** propagation across calls (gateways, async hops). [16](https://github.com/instana/instana-otel-collector)
3. Generate traffic; verify spans and topology mapping in Instana. [16](https://github.com/instana/instana-otel-collector)

## Validation checks

- Spans appear under expected services; parent/child relationships intact; searchable attributes present. [16](https://github.com/instana/instana-otel-collector)

## Outputs for assessment

- 2–4 minute clip: code/config snippet → traffic → trace view proving correlation. [16](https://github.com/instana/instana-otel-collector)

## Top troubleshooting cues

- **Wrong service names:** set consistent resource attributes;
- **Missing links:** confirm headers and proxies preserve TraceContext; prefer OTLP exporters. [16](https://github.com/instana/instana-otel-collector)

## Appendix

- Minimal SDK and Collector configs; note that legacy `instanaexporter` is deprecated—use `otlp`. [16](https://github.com/instana/instana-otel-collector)

## References (public docs)

- [OpenTelemetry with Instana (overview)](https://github.com/instana/instana-otel-collector)
- [Instana Distribution of OpenTelemetry Collector (IDOT)](https://www.linkedin.com/pulse/streaming-out-instana-signalsmetricstraceslogs-through-madhu-bhangi-svsfc)
