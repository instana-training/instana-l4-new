# Pattern Card P3 - Smart Alerts & Service Level Objectives (SLOs)

- **Module:** M2 - Deployment & Operations
- **Version:** March 2026

## Intent

Create actionable Service Level Objectives (SLOs) and Smart Alerts that help technical sellers demonstrate how Instana proactively detects degraded performance, error budget burn, and user-impacting issues. Learners will define SLIs, configure SLOs, attach alerting logic (status, error budget, burn rates), and validate alert context and routing. This prepares sellers to explain Instana’s value to clients who require reliability insights and automated early-warning signals.  
(SLO concepts sourced from IBM Docs)  

## Prerequisites

- A monitored service with measurable latency, traffic, availability, or error rate.  
- Ability to induce degraded behavior (examples only: increased latency, failed calls, synthetic test failures).  
- At least one alert channel type supported by your environment (email, webhook, chat, etc.).  

## Example scenario

1. Create an SLO for a service endpoint using a latency SLI with a target such as 99%.  
2. Configure error budget and burn-rate alert thresholds using long+short windows.  
3. Add an alert channel and define routing properties.  
4. Induce a violation to exhaust error budget faster.  
5. Review the triggered alert, drill into SLO dashboard, and present the impact storyline.  


## Build recipe

### Task 1 - Define SLIs and SLOs

**Step 1.1 - Identify the SLI**  

- Choose the metric representing user experience (for example: latency, availability, success ratio). (IBM SLO concepts)  
- Decide if the SLI uses a threshold or ratio approach and identify good vs bad events.

**Step 1.2 - Create the SLO**  

- Open the Service Levels page and click Add SLO. (IBM Docs: Service Levels page overview)  
- Select the blueprint (Latency, Availability, Traffic, Saturation, or Custom).  
- Set target (for example: 99%) and define the SLO time window (rolling or calendar-aligned).

**Step 1.3 - Configure error budget**  

- Review error budget size automatically derived from SLO target (e.g., 1% budget for 99% target).  
- Observe depletion patterns using the SLO dashboard charts.

### Task 2 - Configure Smart Alerts

**Step 2.1 - Choose alert blueprint**  

- Select alert type: Status, Error Budget Used, Burn Rate (long+short windows).  
- For burn-rate: choose single-window or long+short evaluation.

**Step 2.2 - Set alert thresholds**  

- Define long-window threshold (captures slow trend issues).  
- Define short-window threshold (captures fast spikes).  
- Configure evaluation granularity and consecutive violations.

**Step 2.3 - Add alert channels**  

- Navigate to Alert Channels and create an entry (email, webhook, etc.). 
- Add channel to Smart Alert routing configuration.

### Task 3 - Validate alerting behavior

**Step 3.1 - Induce violation**  

- Trigger behavior that breaches your SLO (examples only: artificial latency spike, forced timeouts).  

**Step 3.2 - Observe SLO status change**  

- Open SLO dashboard; examine status, error budget remaining, and burn rate trends.

**Step 3.3 - Review Smart Alert**  

- Confirm alert fire time, blueprint match, and channel delivery.  
- Correlate with service-level traces, logs, or infrastructure events.

## Validation checks

- SLO correctly displays SLI data, target, and error budget.  
- Smart Alert shows expected blueprint and firing logic.  
- Alert channel receives notification.  
- Root-cause narrative links degraded metric -> SLO violation -> Smart Alert.

## Outputs for assessment

- 3–4 minute walkthrough clip: SLI -> SLO -> Smart Alert -> fired alert -> investigation.  
- Screenshot pack: SLO config, chart views, alert configuration, alert event.  
- Brief written summary: What failed, how fast budget burned, what alert triggered.

## Top troubleshooting cues

- No alert triggered → thresholds misconfigured, evaluation windows too long, channel disabled.  
- SLO shows no data → entity not selected or missing SLI metric.  
- Burn-rate alert didn’t fire → long+short window thresholds too lenient.  
- Alert delivery failure → routing target incorrect or channel not operational.

## Appendix

- Example burn-rate configurations (long window: 1h @ 2x burn; short window: 5m @ 10x burn).  
- Naming convention: <service>-<slo-type>-<target> (example only).

## References (public docs)

- [Managing Events and Alerts](https://www.ibm.com/docs/en/instana-observability/1.0.315?topic=instana-managing-events-alerts)
- [Smart Alerts for Service Level Objectives](https://www.ibm.com/docs/en/instana-observability/1.0.315?topic=slos-smart-alerts-service-level-objectives)
- [Adaptive thresholds in Smart Alerts](https://www.ibm.com/docs/en/instana-observability/1.0.315?topic=instana-adaptive-thresholds-in-smart-alerts) 
- [Service Level Objectives (SLOs) overview](https://www.ibm.com/docs/en/instana-observability/1.0.315?topic=instana-service-level-objectives-slos)
- [Getting started with Service Level Objectives](https://www.ibm.com/docs/en/instana-observability/1.0.315?topic=slos-getting-started-service-level-objectives)
