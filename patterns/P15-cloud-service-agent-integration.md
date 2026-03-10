# Pattern Card P15 — Cloud service agent integration

**Module:** M2 — Deployment & Operations  
**Version:** March 2026

## Intent

Configure cloud monitoring for AWS/Azure/GCP; enable cloud service integrations using IAM roles, service principals, or API keys; validate ingestion of cloud entities. 

## Prerequisites

- Instana tenant with cloud agent or integration feature enabled. 
- Cloud provider account(s) with appropriate IAM/permissions for resource discovery and metrics collection. 
- Supporting documentation for each cloud provider's role/principal requirements. 

## Example scenario

Create an IAM role in AWS and attach to Instana backend or agent; configure AWS integration in Instana UI; assign zones and tags; validate discovery of EC2, RDS, ELB, and other services; confirm metrics flowing into dashboards. 

## Build recipe

1. **Prepare cloud provider credentials:** Create IAM role (AWS), service principal (Azure), or service account key (GCP) with appropriate read permissions for resource discovery. 
2. **Configure integration in Instana:** Open **Settings → Integrations** or cloud agent section; add cloud account with credentials; set zone, region filters, and organizational tags. 
3. **Validate discovery:** Monitor cloud dashboard for entity count; verify at least two service types (e.g., compute + database) appear with live metrics. 
4. **Correlate with infrastructure:** Link cloud entities to Instana-monitored applications or infrastructure to show end-to-end visibility. 

## Validation checks

- Cloud integration connected and authenticated. 
- Cloud resource entities appearing in Instana UI with live metrics. 
- Metrics flowing for multiple service types (compute, database, load balancer, etc.). 
- Cross-correlation between cloud and Instana infrastructure visible (optional: application → cloud service dependency). 

## Outputs for assessment

- Screenshots showing cloud integration configuration, discovered entities, and live metrics. 
- 2–4 minute clip: integration setup → entity discovery → metrics dashboard → correlation example. 

## Top troubleshooting cues

- **Integration not connecting:** verify IAM role/service principal permissions and Instana backend network egress. 
- **Partial entity discovery:** check region filters, resource tags, and scope of assigned permissions. 
- **Missing metrics:** confirm integration health (connection status) and metric-collection service operational. 

## Appendix

- Sample IAM policy documents for AWS, Azure, GCP. 
- Common tagging and naming conventions for cloud resource organization. 

## References (public docs)

- [Cloud service agent configuration](https://www.ibm.com/docs/en/instana-observability)
- [AWS integration setup](https://www.ibm.com/docs/en/instana-observability)
- [Azure integration setup](https://www.ibm.com/docs/en/instana-observability)
- [GCP integration setup](https://www.ibm.com/docs/en/instana-observability)