# Pattern Card P6 — OpenAPI & REST integration

**Module:** M4 — Integrations & Automation  
**Version:** March 2026

## Intent

Consume Instana REST API for data export or enrichment; demonstrate authentication, endpoint usage, pagination/rate limits, and error handling. [10](https://github.com/instana/openapi)

## Prerequisites

- Instana **API token** and base URL; optional downstream target (webhook/BI). [10](https://github.com/instana/openapi)

## Example scenario

Query application/service metrics and push a summarized KPI payload to an external webhook, handling a 401 (bad token) and 429 (rate limit) case. [10](https://github.com/instana/openapi)

## Build recipe

1. Create API token (scope per need) and identify the tenant base URL pattern. [10](https://github.com/instana/openapi)
2. Call a metrics/health endpoint; parse and transform for the external system. [10](https://github.com/instana/openapi)
3. Show handling of **401/429** (retry/backoff or scope fix). [10](https://github.com/instana/openapi)
4. (Optional) Consult the **public OpenAPI** reference to explore more endpoints. [11](https://apitracker.io/a/instana)

## Validation checks

- Authenticated call succeeds; downstream payload accepted; one failure handled correctly. [10](https://github.com/instana/openapi)

## Outputs for assessment

- 3–5 minute clip: token/scopes → successful call → controlled failure+fix → webhook/BI result. [10](https://github.com/instana/openapi)

## Top troubleshooting cues

- **HTTP 401:** wrong token type/scope; **429:** implement backoff, reduce page size. [10](https://github.com/instana/openapi)

## Appendix

- Curl/Postman examples and pagination notes. [10](https://github.com/instana/openapi)

## References (public docs)

- [Getting started with the Instana REST API](https://github.com/instana/openapi)
- [Instana public API (OpenAPI spec)](https://apitracker.io/a/instana)
  ``
