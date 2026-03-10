# Pattern Card P3 — Smart alerts and SLOs

**Module:** M2 — Deployment & Operations  
**Version:** March 2026

## Intent

Create actionable SLOs and Smart Alerts (status, error budget, **burn‑rate** with long/short windows), route notifications, and validate alert context. [7](https://b1stern.github.io/InstanaMiddlewareLab/tutorials/Administration/)

## Prerequisites

- Service with traffic; observable latency/errors (can be induced). [7](https://b1stern.github.io/InstanaMiddlewareLab/tutorials/Administration/)

## Example scenario

Define an SLO for the checkout endpoint’s latency; configure burn‑rate alert windows and a webhook channel; induce a violation and review alert details. [7](https://b1stern.github.io/InstanaMiddlewareLab/tutorials/Administration/)

## Build recipe

1. Define **SLI** & target; create **SLO** and error budget. [7](https://b1stern.github.io/InstanaMiddlewareLab/tutorials/Administration/)
2. Configure **Smart Alert**: choose blueprint (**status/error‑budget/burn‑rate**) and thresholds/time windows. [7](https://b1stern.github.io/InstanaMiddlewareLab/tutorials/Administration/)
3. Add an alert **channel** (e.g., webhook), include custom payload if needed. [7](https://b1stern.github.io/InstanaMiddlewareLab/tutorials/Administration/)
4. Induce violation; review the alert and connected context. [7](https://b1stern.github.io/InstanaMiddlewareLab/tutorials/Administration/)

## Validation checks

- SLO status visible; alert triggered with correct blueprint and routing. [7](https://b1stern.github.io/InstanaMiddlewareLab/tutorials/Administration/)

## Outputs for assessment

- 2–4 minute clip: SLO config → Smart Alert → fired event with action taken. [7](https://b1stern.github.io/InstanaMiddlewareLab/tutorials/Administration/)

## Top troubleshooting cues

- **No alert triggered:** thresholds too strict/lenient; ensure channel permissions and payload format. [7](https://b1stern.github.io/InstanaMiddlewareLab/tutorials/Administration/)

## Appendix

- Naming conventions for SLOs and example burn‑rate windows. [7](https://b1stern.github.io/InstanaMiddlewareLab/tutorials/Administration/)

## References (public docs)

- [Smart Alerts for Service Level Objectives](https://b1stern.github.io/InstanaMiddlewareLab/tutorials/Administration/)
