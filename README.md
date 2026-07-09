# Deborah Lawson | Cybersecurity Analyst Portfolio

A results-driven professional combining a structured analytical methodology with technical threat detection and log analysis to secure enterprise environments.

## 🚀 Featured Cyber Security Projects

| Project Name | Core Competencies | Live Documentation |
| :--- | :--- | :--- |
| **Automated Brute-Force Detection Pipeline** | Elastic Cloud SIEM, Log Ingestion, KQL, Threat Isolation | [View Lab Setup & Telemetry](#objective) |
| **Wireshark Network Traffic Analysis** | Protocol Mechanics, Session Validation, Packet Analysis | [View Standalone Project Repository ↗](https://github.com/Debby-Monroe/Wireshark-Network-Traffic-Analysis) |
| **Automated Brute-Force Detection Pipeline** | Elastic Cloud SIEM, Log Ingestion, KQL, Threat Isolation | [View Lab Setup & Telemetry](#-incident-investigation-report-case-ref-2026-06-bf) |
---

## Hello, I'm a Security Analyst & Compliance-Driven Defender 🔍🛡️

Welcome to my security operations portfolio. I am a detail-oriented professional bridging the gap between structured analytical methodology and technical threat detection.
Coming from a professional background rooted in high-stakes banking operations, complex corporate workflows, and rigorous compliance analysis, I specialize in parsing dense data streams to locate anomalies, identify risks, and enforce security integrity. I have recently transitioned my analytical foundation into the technical domain, graduating from the **Google Cybersecurity Professional program** and engineering my own cloud-native security environments.

I look at security telemetry through a dual lens: understanding the deep technical mechanics of an exploit while maintaining a sharp focus on the broader operational risk and corporate impact.

---

## 🛠️ Tech Stack & Lab Environment

*   **Security Operations (SecOps):** Elastic Cloud SIEM, Log Analysis, Incident Triaging, KQL (Kibana Query Language)
*   **Operating Systems & Virtualization:** Ubuntu Linux Server administration, macOS, Virtual Machine management
*   **Networking & Traffic Analysis:** Packet capture analysis, protocol inspection, network telemetry mapping
*   **Automation & Scripting:** Defensive Bash tooling, Python string parsing, automated security validation scripts
*   **Frameworks & Governance:** NIST Cybersecurity Framework (CSF), Regulatory Compliance Mapping, Risk Mitigation Documentation

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
