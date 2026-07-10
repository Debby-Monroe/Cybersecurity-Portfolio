# Automated Brute-Force Detection & Telemetry Pipeline (Elastic Cloud SIEM)

## Objective
This project establishes an enterprise-grade log ingestion pipeline to detect and analyze brute-force credential attacks against a Linux endpoint. The goal was to simulate an adversarial brute-force dictionary attack, configure centralized log collection, and use Kibana Query Language (KQL) to isolate security anomalies and profile threat actor behavior.

## Tools & Environment Architecture
*   **SIEM Platform:** Elastic Cloud (Kibana Deployment via GCP)
*   **Endpoint System:** Ubuntu Linux Virtual Machine (ARM64 Architecture)
*   **Telemetry Agent:** Elastic Agent (Managed via Fleet)
*   **Attack Vector:** Automated Dictionary Attack Script
*   **Monitored Telemetry:** System Authentication Logs (`/var/log/auth.log`)

---

## Technical Execution & Walkthrough

## 1 Ingestion Infrastructure Setup

- Deployed an Elastic Cloud environment to function as a centralized Security Information and Event Management (SIEM) platform.
- Configured a Fleet Management policy to manage endpoint telemetry and security monitoring.
- Installed Elastic Agent on an Ubuntu endpoint and enrolled it into Fleet using a secure enrollment token.
- Validated successful agent enrollment and confirmed continuous log ingestion from the endpoint.
- Established a foundation for security monitoring, threat detection, and incident investigation within Elastic Security.

## Key Result

Successfully onboarded an Ubuntu endpoint into Elastic Security, enabling centralized collection and analysis of authentication, process, and system activity logs.
<img width="1412" height="883" alt="Screenshot 2026-07-06 at 7 13 51 PM" src="https://github.com/user-attachments/assets/9797e8b1-c63d-4eb7-afc7-d5a9616f94d2" />


### 2. Adversarial Simulation
*   Executed an automated dictionary script on the endpoint to generate a rapid succession of failed authentication attempts, simulating an unauthenticated external threat actor attempting to guess local credentials.

### 3. SIEM Triaging & Log Analysis
*   Pivoted to the Kibana **Discover** panel to analyze raw log indices, applying a temporal filter to capture the spike in data.
*   Utilized the KQL query statement `event.outcome : "failure"` to filter out routine system noise and isolate the unauthorized activity.

<img width="1366" height="827" alt="Screenshot 2026-07-06 at 7 15 41 PM" src="https://github.com/user-attachments/assets/cb8628d6-b87a-4110-a269-ff4074f5b2e2" />


---

## Analyst Findings & Security Insights

The telemetry pipeline successfully captured **47 total authentication failures**. Upon granular inspection of the data fields, a distinct attack signature was mapped:

| Metric | Analytical Value |
| --- | --- |
| **Attack Signature** | Rapid, automated credential stuffing / multi-account dictionary attack. |
| **Target Profiles** | System default accounts (`admin`, `database`, `guest`, `support`, `test`). |
| **Anomalous Field** | High concentration of failure logs containing the user string `deborah-lawson`. |

<img width="540" height="657" alt="Screenshot 2026-07-06 at 7 29 18 PM" src="https://github.com/user-attachments/assets/c4322e55-7106-44f8-97d8-a1d232e824b8" />


### Key Takeaway
The threat actor was not targeting a single user; instead, they were sweeping for high-privilege default accounts (`database`, `admin`) to establish an initial foothold and achieve rapid privilege escalation. Identifying this pattern allows security teams to quickly enforce account lockout policies and audit default, unhardened credentials.
