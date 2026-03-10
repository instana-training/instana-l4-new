# Pattern Card P9 — Security signals & vulnerability views

**Module:** M5 — Security & Governance  
**Version:** March 2026

## Intent

Use Instana security insights in context and configure **RBAC/SSO/MFA** to enforce least‑privilege and governed access. [12](https://www.ibm.com/docs/en/instana-observability/1.0.312?topic=instana-configuring-authentication)

## Prerequisites

- Admin access to **Security & Access** and **Authentication**; test app with demo security signals or sample data. [12](https://www.ibm.com/docs/en/instana-observability/1.0.312?topic=instana-configuring-authentication)[13](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=kubernetes-installing-agent)

## Example scenario

Create roles/teams scoped to a set of applications or K8s namespaces; configure SSO; triage one security signal and identify the owning service. [12](https://www.ibm.com/docs/en/instana-observability/1.0.312?topic=instana-configuring-authentication)[13](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=kubernetes-installing-agent)

## Build recipe

1. Define **roles/teams** with scoped access (applications, K8s, logs, DEM). [12](https://www.ibm.com/docs/en/instana-observability/1.0.312?topic=instana-configuring-authentication)
2. Configure **SAML/IdP** and test SSO; explain MFA practice. [13](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=kubernetes-installing-agent)
3. Open a **security/vulnerability** view and link to the affected service; create a ticket if needed. [12](https://www.ibm.com/docs/en/instana-observability/1.0.312?topic=instana-configuring-authentication)

## Validation checks

- Scoped RBAC works; SSO login verified; a security signal triaged to the right owner. [12](https://www.ibm.com/docs/en/instana-observability/1.0.312?topic=instana-configuring-authentication)[13](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=kubernetes-installing-agent)

## Outputs for assessment

- 3–4 minute clip: RBAC/SSO demo + one triaged security finding in context. [12](https://www.ibm.com/docs/en/instana-observability/1.0.312?topic=instana-configuring-authentication)

## Top troubleshooting cues

- **Role confusion:** review permission lists and scope bindings; check audit trail if access is denied. [12](https://www.ibm.com/docs/en/instana-observability/1.0.312?topic=instana-configuring-authentication)

## Appendix

- Example team → scope matrix and SSO group‑mapping notes. [13](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=kubernetes-installing-agent)

## References (public docs)

- [Administering Instana (RBAC & access)](https://www.ibm.com/docs/en/instana-observability/1.0.312?topic=instana-configuring-authentication)
- [Configuring authentication (SSO/MFA/IdP)](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=kubernetes-installing-agent)
