# Module M5 — Security & Governance

**Capability goal:** Configure secure access (RBAC/SSO/MFA), show audit/usage views, and present **cost/efficiency** insights that inform operational decisions. [14](https://www.ibm.com/docs/en/instana-observability/1.0.312?topic=instana-configuring-authentication)[15](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=kubernetes-installing-agent)[16](https://pkg.go.dev/github.com/instana/instana-agent-operator)

**Primary outcomes:** O11 (Security & governance), O14 (Cost insights / FinOps) [14](https://www.ibm.com/docs/en/instana-observability/1.0.312?topic=instana-configuring-authentication)

---

## What you will be able to demonstrate

1. Create and assign **roles/teams** with limited scopes for apps/K8s/logs/DEM/synthetics; configure **SSO/MFA** and explain least‑privilege choices. [14](https://www.ibm.com/docs/en/instana-observability/1.0.312?topic=instana-configuring-authentication)[15](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=kubernetes-installing-agent)
2. Present **usage/billing** and design a **cost‑aware dashboard** (e.g., efficiency KPIs) using thresholds to spotlight outliers. [14](https://www.ibm.com/docs/en/instana-observability/1.0.312?topic=instana-configuring-authentication)[16](https://pkg.go.dev/github.com/instana/instana-agent-operator)

---

## Pattern cards in this module

- **P9 Security signals & vulnerability views** (O11) — RBAC/SSO setup and security triage in service context. [14](https://www.ibm.com/docs/en/instana-observability/1.0.312?topic=instana-configuring-authentication)[15](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=kubernetes-installing-agent)
- **P12 Cost Insights & FinOps** (O14) — performance + cost/efficiency views and an optimization recommendation. [14](https://www.ibm.com/docs/en/instana-observability/1.0.312?topic=instana-configuring-authentication)[16](https://pkg.go.dev/github.com/instana/instana-agent-operator)

---

## Prerequisites

- Admin access for **Security & Access** and **Authentication** settings; tenant with usage/billing visibility. [14](https://www.ibm.com/docs/en/instana-observability/1.0.312?topic=instana-configuring-authentication)

---

## Build recipe (suggested sequence)

1. **RBAC + SSO/MFA**
   - Define roles/teams; assign scoped access; configure SAML/IdP and test login. Explain why the scopes match team responsibilities. [14](https://www.ibm.com/docs/en/instana-observability/1.0.312?topic=instana-configuring-authentication)[15](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=kubernetes-installing-agent)
2. **Cost/Efficiency insights**
   - Navigate usage/billing; create a dashboard combining performance KPIs with cost/efficiency metrics; apply **thresholds on table widgets** to highlight anomalies. [14](https://www.ibm.com/docs/en/instana-observability/1.0.312?topic=instana-configuring-authentication)[16](https://pkg.go.dev/github.com/instana/instana-agent-operator)

---

## Completion evidence

- **Video** showing:
  - Working SSO and scoped RBAC roles;
  - A cost‑aware dashboard with a clear optimization proposal and expected impact. [15](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=kubernetes-installing-agent)[16](https://pkg.go.dev/github.com/instana/instana-agent-operator)

---

## References (public docs)

- [Administering Instana (RBAC/Access, usage/billing)](https://www.ibm.com/docs/en/instana-observability/1.0.312?topic=instana-configuring-authentication) · [Configuring authentication (SSO/MFA/IdP)](https://www.ibm.com/docs/en/instana-observability/1.0.314?topic=kubernetes-installing-agent)
- [Build 286 – threshold on table widget (dashboards)](https://pkg.go.dev/github.com/instana/instana-agent-operator)
  ``
