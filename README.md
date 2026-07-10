# Deborah Lawson | Cybersecurity Analyst Portfolio

A results-driven professional combining a structured analytical methodology with technical threat detection and log analysis to secure enterprise environments.

## 🚀 Featured Cyber Security Projects

| Project Name | Core Competencies | Live Documentation |
| :--- | :--- | :--- |
| [Automated Brute-Force Detection Pipeline](#-automated-brute-force-detection--telemetry-pipeline-elastic-cloud-siem) | Elastic Cloud SIEM, Log Ingestion, KQL, Threat Isolation | [View Lab Setup & Telemetry](#-incident-investigation-report-case-ref-2026-06-bf) |
| [Wireshark Network Traffic Analysis](https://github.com/Debby-Monroe/Wireshark-Network-Traffic-Analysis) | Protocol Mechanics, Session Validation, Packet Analysis | [View Standalone Project Repository ↗](https://github.com/Debby-Monroe/Wireshark-Network-Traffic-Analysis) |
---

# Security Analyst & Compliance-Driven Defender 🔍🛡️

Welcome to my cybersecurity portfolio.

I am a detail-oriented Security Analyst focused on threat detection, security operations, and compliance-driven defense. With a professional background in high-stakes banking operations, complex corporate workflows, and structured risk analysis, I bring a strong foundation in identifying anomalies, investigating operational risks, and maintaining data integrity in regulated environments.

I have expanded this analytical foundation into cybersecurity by completing the **Google Cybersecurity Professional Certificate** and developing hands-on experience through self-engineered security environments. My projects involve building cloud-based SIEM solutions, analyzing authentication telemetry, investigating suspicious activity, and simulating adversarial techniques to better understand real-world attack patterns.

I approach cybersecurity through a dual lens: understanding the technical mechanics behind threats while evaluating their broader business and operational impact. My focus is transforming security data into actionable intelligence that helps organizations detect threats, strengthen controls, and improve overall security resilience.

**Core Focus Areas:**

* Security Operations Center (SOC) Analysis
* SIEM Deployment & Security Monitoring
* Log Analysis & Threat Investigation
* Linux Security & Authentication Monitoring
* Incident Detection & Response Workflows
* Compliance & Risk Assessment
* Security Documentation & Reporting
* Threat Intelligence Fundamentals


---

## Tech Stack & Lab Environment

### SIEM & Security Tools
- Elastic Cloud
- Kibana
- Elastic Agent
- Fleet Management

### Operating Systems
- Ubuntu Linux
- macOS

### Cloud
- Google Cloud Platform (GCP)

### Languages & Scripting
- Bash
- Python

### Networking
- SSH
- TCP/IP
- Linux Authentication Logs

### Frameworks
- NIST Cybersecurity Framework (CSF)
---

## 🔬 Active Security Projects

### 🚨 [Automated Brute-Force Detection & Telemetry Pipeline (Elastic Cloud SIEM)](https://github.com/Debby-Monroe/Cybersecurity-Portfolio)
### 🛑 Incident Investigation Report: Case Ref #2026-06-BF

**Status:** Closed / Remediated  
**Severity:** Medium  
**Handler:** Deborah Lawson (SOC Analyst)

---

#### 1. Executive Summary
On June 29, 2026, an automated alert triggered within the Elastic Cloud SIEM environment indicating an anomalous spike in authentication failures against a core virtual asset (deborah-lawson-qemu-virtual-machine). Initial triage confirmed a targeted brute-force dictionary attack attempting to gain unauthorized SSH access. A total of 47 failed authentication attempts were isolated and analyzed. The threat was successfully mitigated with zero system compromise.

#### 2. Incident Timeline & Detection Metrics
*   **Initial Alert Trigger / Window:** 2026-06-29 @ 19:49:26 to 19:49:32 UTC
*   **Total Log Events Correlated:** 47 Failed Login Attempts
*   **Target Accounts Enumerated:** `admin`, `guest`
*   **Attacker Source IP:** `127.0.0.1` (Local Loopback / Simulation Interface)
*   **Target Destination Host:** `deborah-lawson-qemu-virtual-machine`

#### 3. Investigative Methodology (KQL Analysis)
To isolate the malicious telemetry within Kibana, the following Kibana Query Language (KQL) string was executed to filter out background noise and focus strictly on the authentication anomalies:

```kql
event.outcome : "failure"
```
*   **The Mission:** Engineered an absolute log ingestion infrastructure mapping an Ubuntu endpoint directly to a cloud-hosted Elastic SIEM instance. Simulated an active dictionary attack to profile threat actor behavior and analyze raw endpoint telemetry.
*   **Core Skills:** Fleet Management, Elastic Agent Deployment, Linux System Auditing (`auth.log`), KQL Query Optimization.

### 🌐 [Network Traffic Analysis & Protocol Triage](https://github.com/Debby-Monroe/Wireshark-Network-Traffic-Analysis)

*   **The Mission:** Dissecting malicious packet captures (PCAPs) to identify command-and-control (C2) traffic beacons, unauthorized file exfiltration, and local network compromises.
*   **Core Skills:** Wireshark filtering, OSI Model mapping, protocol anomaly identification.


---

## 📈 The Analytical Edge I Bring

> **"A security log is just a ledger waiting to be audited."**
> 
> My past experience taught me how to navigate strict regulatory landscapes and spot microscopic discrepancies in massive volumes of documentation. In a Security Operations Center (SOC), I apply that exact same investigative stamina. Whether it is an unmapped regulatory compliance failure or a subterranean string pattern buried in 47 failed login attempts, my objective remains identical: isolate the threat, document the footprint, and protect the organization.

---

## 📬 Let's Connect

*   **LinkedIn:** [www.linkedin.com/in/deborah-lawson-6432b936a](https://www.linkedin.com/in/deborah-lawson-6432b936a)
*   **Professional Portfolio Index:** You are currently exploring it! Check out my repositories for raw documentation, scripts, and deployment configurations.
