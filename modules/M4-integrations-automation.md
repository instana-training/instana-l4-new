# Module M4 — Integrations & Automation

**Capability goal:** Integrate Instana with external systems/flows via **REST/OpenAPI/OTLP** and implement **safe, testable automation** with the **Action Catalog** and policies. [11](https://github.com/instana/openapi)[12](https://www.ibm.com/docs/en/instana-observability/current?topic=capabilities-intelligent-remediation)

**Primary outcomes:** O9 (Integrations & APIs), O12 (Automated RCA & remediation) [11](https://github.com/instana/openapi)[12](https://www.ibm.com/docs/en/instana-observability/current?topic=capabilities-intelligent-remediation)

---

## What you will be able to demonstrate

1. Authenticate and call **Instana REST APIs** (tokens, scopes, base URL), handle pagination and rate limits, and wire results to a downstream consumer. [11](https://github.com/instana/openapi)
2. Define and run **automation actions** (Manual/Script/HTTP/Issue/Ansible), parameterize securely, and link them to events using **policies**. [12](https://www.ibm.com/docs/en/instana-observability/current?topic=capabilities-intelligent-remediation)[13](https://images.g2crowd.com/uploads/attachment/file/1444513/IBM-Instana-Observability.pdf)

---

## Pattern cards in this module

- **P6 OpenAPI & REST integration** (O9) — export metrics/health and push to a webhook/BI; show error handling (401/429). [11](https://github.com/instana/openapi)
- **P10 Automated RCA & remediation** (O12) — build a guarded remediation workflow, record action history, and validate outcomes. [12](https://www.ibm.com/docs/en/instana-observability/current?topic=capabilities-intelligent-remediation)[13](https://images.g2crowd.com/uploads/attachment/file/1444513/IBM-Instana-Observability.pdf)

---

## Prerequisites

- **API token** with appropriate scope; optional external target (webhook/issue tracker/Ansible). [11](https://github.com/instana/openapi)
- Permissions to create **automation actions** and **policies** in the tenant. [13](https://images.g2crowd.com/uploads/attachment/file/1444513/IBM-Instana-Observability.pdf)

---

## Build recipe (suggested sequence)

1. **REST API usage**
   - Create token; call catalog/metrics endpoints; demonstrate pagination/rate‑limit handling; document base URL patterns. [11](https://github.com/instana/openapi)
2. **Action Catalog & policy**
   - Create a script or HTTP action with static/vault/dynamic parameters; attach to an Instana event via a policy; run once manually, then automatically; review action history. [12](https://www.ibm.com/docs/en/instana-observability/current?topic=capabilities-intelligent-remediation)[13](https://images.g2crowd.com/uploads/attachment/file/1444513/IBM-Instana-Observability.pdf)

---

## Completion evidence

- **Video** showing:
  - One successful API flow and one controlled failure + fix;
  - A recommended action/policy execution with auditable results and safety gates. [11](https://github.com/instana/openapi)[13](https://images.g2crowd.com/uploads/attachment/file/1444513/IBM-Instana-Observability.pdf)

---

## References (public docs)

- [Getting started with the Instana REST API](https://github.com/instana/openapi) · [Action catalog](https://www.ibm.com/docs/en/instana-observability/current?topic=capabilities-intelligent-remediation) · [Managing actions & policies](https://images.g2crowd.com/uploads/attachment/file/1444513/IBM-Instana-Observability.pdf)
