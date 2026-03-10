# Module M3 — Digital Experience Monitoring

**Capability goal:** Measure and improve user experience through **Real User Monitoring** (RUM/Session Replay) and **Synthetic** testing; correlate frontend signals with backend traces. [9](https://registry.terraform.io/providers/instana/instana/latest/docs/resources/rbac_role)[10](https://github.com/instana/synthetic-synctl)

**Primary outcomes:** O6 (DEM: RUM/Replay), O7 (Synthetic) [9](https://registry.terraform.io/providers/instana/instana/latest/docs/resources/rbac_role)[10](https://github.com/instana/synthetic-synctl)

---

## What you will be able to demonstrate

1. Instrument a web (or mobile) app for **RUM** and **Session Replay** and connect a poor UX session to backend traces. [9](https://registry.terraform.io/providers/instana/instana/latest/docs/resources/rbac_role)
2. Create **API** and/or **browser** synthetic tests, schedule across locations, and triage a failing run using waterfalls/HAR/logs. [10](https://github.com/instana/synthetic-synctl)

---

## Pattern cards in this module

- **P4 RUM for Web & Mobile** (O6) — add RUM, validate beacons, analyze Session Replay and backend correlation. [9](https://registry.terraform.io/providers/instana/instana/latest/docs/resources/rbac_role)
- **P5 Synthetic monitoring** (O7) — build API/Browser synthetics, induce a failure, and diagnose root cause. [10](https://github.com/instana/synthetic-synctl)

---

## Prerequisites

- Access to a **test website/app** to inject the RUM snippet/SDK; permissions to run synthetics against target URLs/APIs. [9](https://registry.terraform.io/providers/instana/instana/latest/docs/resources/rbac_role)

---

## Build recipe (suggested sequence)

1. **Enable RUM**
   - Add JavaScript snippet/SDK; validate beacons; explore **Websites & Mobile Apps** dashboards and open a **Session Replay**. Link to a backend trace via correlation. [9](https://registry.terraform.io/providers/instana/instana/latest/docs/resources/rbac_role)
2. **Create Synthetic tests**
   - Configure API and/or Browser tests; choose locations; trigger a controlled failure; use network waterfall/HAR and backend signals to diagnose. [10](https://github.com/instana/synthetic-synctl)

---

## Completion evidence

- **Video** showing:
  - One Session Replay tied to a backend trace that explains UX degradation;
  - A synthetic test going **green → red** with diagnosis and a remediation/next step. [9](https://registry.terraform.io/providers/instana/instana/latest/docs/resources/rbac_role)[10](https://github.com/instana/synthetic-synctl)

---

## References (public docs)

- [Monitoring websites (RUM/Session Replay)](https://registry.terraform.io/providers/instana/instana/latest/docs/resources/rbac_role) · [Synthetic monitoring](https://github.com/instana/synthetic-synctl)
