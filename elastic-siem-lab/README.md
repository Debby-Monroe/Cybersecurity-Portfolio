# Automated Brute-Force Detection & Telemetry Pipeline (Elastic Cloud SIEM)

## Objective

This project demonstrates the deployment of an Elastic SIEM environment to collect and analyze security logs from a Linux endpoint. The goal was to simulate a brute-force dictionary attack, configure centralized log collection using Elastic Agent, and investigate authentication failures using Kibana Query Language (KQL).

The investigation focused on identifying suspicious login activity, analyzing authentication patterns, and understanding how SIEM platforms can be used to detect and investigate potential unauthorized access attempts.

## Tools & Environment Architecture

### 🖥️ Lab Architecture Components

* **SIEM Platform:** Elastic Cloud with Kibana Security (Deployed via GCP)
* **Endpoint System:** Ubuntu Linux Virtual Machine (ARM64 Architecture)
* **Telemetry Collection:** Elastic Agent managed through Fleet Management
* **Attack Simulation:** Automated dictionary attack script generating failed authentication events
* **Log Source:** Linux authentication logs (`/var/log/auth.log`) collected for security analysis
  
#### Architecture Overview

The lab environment consisted of an Ubuntu Linux endpoint connected to an Elastic Cloud SIEM platform through Elastic Agent. Fleet Management was used to manage endpoint configuration and telemetry collection. Authentication logs were forwarded to Kibana for investigation and analysis of simulated brute-force activity.

---Fleet Management was used to manage endpoint configuration and telemetry collection. Authentication logs were forwarded to Kibana for investigation and analysis of simulated brute-force activity.
---

## Technical Execution & Walkthrough

##  Ingestion Infrastructure Setup

- Deployed an Elastic Cloud environment to function as a centralized Security Information and Event Management (SIEM) platform.
- Configured a Fleet Management policy to manage endpoint telemetry and security monitoring.
- Installed Elastic Agent on an Ubuntu endpoint and enrolled it into Fleet using a secure enrollment token.
- Validated successful agent enrollment and confirmed continuous log ingestion from the endpoint.
- Established a foundation for security monitoring, threat detection, and incident investigation within Elastic Security.

## Key Result

Successfully onboarded an Ubuntu endpoint into Elastic Security, enabling centralized collection and analysis of authentication, process, and system activity logs.
<img width="1412" height="883" alt="Screenshot 2026-07-06 at 7 13 51 PM" src="https://github.com/user-attachments/assets/9797e8b1-c63d-4eb7-afc7-d5a9616f94d2" />


## Adversarial Simulation

- Simulated a password-guessing attack by generating multiple failed authentication attempts on the Ubuntu endpoint.
- Created a series of unsuccessful login events to emulate unauthorized access attempts against local user accounts.
- Generated security-relevant telemetry for analysis within the Elastic SIEM environment.

## SIEM Investigation & Log Analysis

- Investigated collected endpoint logs using Kibana Discover.
- Applied time-based filtering to identify spikes in authentication-related activity.
- Utilized the KQL query:

  event.outcome:"failure"

  to isolate failed authentication events from normal system activity.
- Reviewed event details, timestamps, and targeted accounts to assess the nature of the activity.
- Confirmed successful log ingestion and visibility of authentication failures within Elastic Security.

## Findings

- Multiple failed authentication events were detected during the testing period.
- Authentication failures targeted several user accounts in rapid succession.
- The activity pattern was consistent with a password-guessing or brute-force attack simulation.
- Elastic Security successfully captured and indexed the events, enabling rapid investigation and triage.

## Outcome

Successfully demonstrated the ability to generate, detect, investigate, and document suspicious authentication activity using Elastic SIEM, Kibana Discover, and KQL-based log analysis.
<img width="1366" height="827" alt="Screenshot 2026-07-06 at 7 15 41 PM" src="https://github.com/user-attachments/assets/cb8628d6-b87a-4110-a269-ff4074f5b2e2" />


---

## Analyst Findings & Security Insights

The Elastic SIEM environment successfully captured and indexed 47 authentication failure events generated during the simulation. Analysis of the event data revealed a pattern consistent with an automated password-guessing attack targeting multiple user accounts.

| Metric | Observation |
|----------|-------------|
| Attack Pattern | Automated multi-account dictionary attack simulation |
| Authentication Failures | 47 failed login attempts detected |
| Targeted Accounts | admin, database, guest, support, test |
| Timeline | Authentication failures occurred in rapid succession |
| Detection Method | KQL query: `event.outcome:"failure"` |
| Log Source | Ubuntu endpoint monitored by Elastic Agent |

### Security Analysis

- Multiple authentication failures were observed across several commonly used account names.
- The frequency and timing of the events suggest automated activity rather than normal user behavior.
- Event logs provided clear visibility into the failed login attempts, enabling rapid investigation and triage.
- Elastic Security successfully captured, indexed, and presented the authentication events for analysis.

### Conclusion

The investigation demonstrated the effectiveness of Elastic SIEM in detecting and analyzing suspicious authentication activity. The simulated attack generated identifiable indicators that could assist security analysts in recognizing and responding to potential brute-force or dictionary-based attacks in a production environment.

<img width="540" height="657" alt="Screenshot 2026-07-06 at 7 29 18 PM" src="https://github.com/user-attachments/assets/c4322e55-7106-44f8-97d8-a1d232e824b8" />


## Key Takeaway

The simulated threat activity was not focused on a single user account. Instead, multiple commonly targeted default and potentially privileged accounts (`database`, `admin`, `guest`) were tested in rapid succession, indicating a dictionary-based account discovery and password-guessing attempt.

Recognizing this attack pattern allows security teams to prioritize defensive actions such as enforcing account lockout policies, removing or securing unused default accounts, and reviewing authentication monitoring rules for similar activity.
