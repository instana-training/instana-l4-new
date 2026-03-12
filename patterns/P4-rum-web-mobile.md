# Pattern Card P4 - Website Monitoring (RUM & EUM)

- **Module:** M3 - Digital Experience Monitoring
- **Version:** March 2026

## Intent

Provide technical sellers with the ability to demonstrate how Instana monitors real user experience for websites and web applications using Real User Monitoring (RUM). Learners will instrument a website with the lightweight JavaScript agent, analyze beacons, page loads, route transitions, JavaScript errors, and core web vitals, and correlate frontend behavior with backend traces. This prepares sellers to address common client pain points including slow page loads, frontend errors, inconsistent SPA behavior, and lack of visibility from browser to backend.  

## Prerequisites

- Access to a website or web application where a tracking script can be embedded.  
- Ability to generate user traffic (manual or synthetic).  
- Permissions to configure CSP/allowlists if needed for beacon transmission.  

## Example scenario

1. Add a website in the Instana UI and receive the JavaScript snippet.  
2. Embed the tracking script; verify beacons flowing into the dashboard.  
3. Identify pages with high load times, JS errors, or slow route transitions.  
4. Open a session trace/view and correlate frontend actions to backend calls.  
5. Recommend improvements based on findings.  
(Supported by IBM website monitoring overview.)

## Build recipe

### Task 1 - Instrument website

**Step 1.1 - Add website**  

- Navigate to **Websites & Mobile Apps** and click **Add Website**. 
- Provide a display name and confirm the domain.

**Step 1.2 - Add tracking snippet**  

- Copy the JavaScript tracking snippet and insert into the `<head>` of all pages or template.  
- For SPA frameworks, enable automatic page transition detection.

**Step 1.3 - Optional security controls**  

- Enable Subresource Integrity (SRI) if required. 
- Confirm Content-Security-Policy allows agent script and beacon URLs.

### Task 2 - Validate real user data

**Step 2.1 - Confirm beacons**  

- Navigate to the Website dashboard and verify incoming beacon counts.  

**Step 2.2 - Analyze performance**  

- Review page load metrics: DNS, TCP, TTFB, render, ready, load events.  
- Identify slow routes and investigate waterfall timing.

**Step 2.3 - Error analysis**  

- Examine JavaScript error frequency, categories, and affected browsers/OS. 
- Determine if errors relate to SPA transitions or missing resources.

### Task 3 - Connect frontend to backend

**Step 3.1 - Open website trace**  

- Select a session or page load and open the **Website Trace** view. 

**Step 3.2 - Correlate with backend**  

- Jump from frontend events to backend service traces.  
- Review latency, errors, and downstream calls.

### Task 4 - Optimization insights (optional)

**Step 4.1 - Geolocation**  

- Compare performance by region.  

**Step 4.2 - Browser/Device**  

- Determine whether specific browsers or devices have degraded experience.

## Validation checks

- Website dashboard shows active sessions and beacon data.  
- At least one page load sample links to a backend trace.  
- JavaScript error insights visible for at least one route.  
- SPA navigation captured if applicable.

## Outputs for assessment

- 3–4 minute clip: setup → beacons → website dashboard → website trace → backend trace.  
- Screenshots: RUM install, dashboard metrics, JS errors, correlated trace.  
- Summary: root cause explanation of performance or UX issue.

## Top troubleshooting cues

- **No data flowing** → script not loaded, CSP blocking beacons, SRI mismatch.  
- **High JS errors** → missing libraries, incompatible browser versions.  
- **Slow SPA transitions** → identify long-running render events or heavy client-side code.  
- **Trace correlation missing** → missing correlation headers or backend not instrumented.

## Appendix

- Note on SPA auto-transition detection.  
- SRI best practices.  

## References (public docs)

- [Monitoring websites (RUM)](https://www.ibm.com/docs/en/instana-observability/1.0.315?topic=instana-monitoring-websites)
- [Website monitoring FAQ](https://www.ibm.com/docs/en/instana-observability/1.0.315?topic=websites-website-monitoring-faq)
- [Backend correlation](https://www.ibm.com/docs/en/instana-observability/1.0.315?topic=websites-backend-correlation)