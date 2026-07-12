# 🚨 Automated Brute-Force Detection & Telemetry Pipeline (Elastic Cloud SIEM)

## 🛠️ Project Overview
This project shows how to set up a cloud-based Elastic SIEM to collect security logs from a remote Linux server. The goal of this lab was to configure log collection using the Elastic Agent, simulate a brute-force password attack, and investigate the failed login logs using Kibana Query Language (KQL).

### 🎯 Core Skills Demonstrated:
* **SIEM Setup & Management:** Registering endpoints and installing cloud-managed Elastic Agents using Fleet.
* **Log Ingestion & Monitoring:** Monitoring Linux authentication logs (`/var/log/auth.log`) to spot unusual activity.
* **Incident Analysis & Reporting:** Using KQL searches to isolate attack patterns and document the findings.

---

## 🧱 Lab Architecture & Tooling
* **SIEM Platform:** Elastic Cloud with Kibana Security (Deployed on GCP)
* **Endpoint System:** Ubuntu Linux VM (ARM64 Architecture)
* **Log Collection Tool:** Elastic Agent managed through Fleet Management
* **Monitored Log Source:** Linux Authentication Logs (`auth.log`)

---

## ⚡ Technical Execution Steps

### 1. Setting Up the SIEM Configuration
* Created an Elastic Cloud account and opened the Kibana Security workspace.
* Configured the Fleet Management page and generated enrollment tokens for the server.
* Installed the Elastic Agent onto the Ubuntu virtual machine so it could start sending logs to the cloud.

### 2. Verifying Log Ingestion
* Turned on the Linux System integration policy inside Fleet.
* Pointed the agent to look at the `/var/log/auth.log` file path.
* Verified that the real-time logs were showing up properly inside the Kibana Discover dashboard.

<img width="1412" height="883" alt="Screenshot 2026-07-06 at 7 13 51 PM" src="https://github.com/user-attachments/assets/9797e8b1-c63d-4eb7-afc7-d5a9616f94d2" />

---

## 🕵️‍♂️ Incident Investigation Report: Case Ref #2026-06-BF

**Status:** Closed / Resolved  
**Severity:** Medium  
**Assigned Analyst:** Deborah Lawson (SOC Analyst)

### 1. Executive Summary
On June 29, 2026, an automated password-guessing attack was simulated against the monitored Ubuntu server to generate security logs. The attack created a large spike in failed SSH login attempts. 

The security pipeline successfully caught **47 failed login events** in just a few seconds. The attack targeted multiple default and administrative accounts. No successful logins occurred, and the server remained safe and secure.

### 2. Detection Timeline & Footprint
* **Time of Attack:** 2026-06-29 @ 19:49:26 – 19:49:32 UTC
* **Total Volume:** 47 failed login attempts
* **Target Accounts Checked:** `admin`, `database`, `guest`, `support`, `test`
* **Source IP Address:** `127.0.0.1` (Local simulation environment)
* **Target System:** `deborah-lawson-qemu-virtual-machine`

### 3. Kibana Query Language (KQL) Filtering
To separate the attack traffic from normal background system logs, I applied this specific filter inside the Kibana Discover workspace:

```kql
event.outcome : "failure"
```

This query made it easy to filter out normal system logs so I could immediately look at the timestamps, how often the attacks happened, and which user accounts were targeted.

---

## 📊 Analyst Findings & Security Insights

The logs clearly show an automated password-guessing attack rather than a regular user making a typo. I know this because multiple different usernames were tried in a very short amount of time.

| Investigation Metric | Telemetry Observation Summary |
| :--- | :--- |
| **Attack Type** | Automated password-guessing attack |
| **Total Logged Failures** | 47 separate failed login events |
| **Targeted Accounts** | Generic names (`admin`, `database`, `guest`, `support`, `test`) |
| **Time Frame** | All attacks happened sequentially within a few seconds |
| **Log Source** | Collected from the Ubuntu `auth.log` file using Elastic Agent |

---

## 🛑 Strategic Recommendations

* **Enforce Account Lockout Policies:** Set a limit on failed login attempts to automatically freeze an account if someone inputs the wrong password too many times in a row.
* **Disable Default Accounts:** Turn off or remove generic account names like `admin` and `guest` so attackers do not have easy, predictable targets to scan.
* **Set Up Monitoring Alerts:** Configure alert thresholds in Elastic SIEM to flag an endpoint if it experiences more than 10 failed login attempts within a single minute.

---

## 📝 Key Takeaway

This project gave me hands-on experience with the entire security monitoring process—from setting up log pipelines to investigating real threat data and writing a summary report. It proves my ability to use a SIEM to track suspicious login activity, identify basic attack patterns, and suggest ways to keep a system safe.
