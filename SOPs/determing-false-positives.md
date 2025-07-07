# SOC 1 Analyst Guide: Determining False Positives

##  Overview
A **false positive** occurs when a security tool flags an activity as malicious, but it's actually benign or expected. SOC 1 Analysts are responsible for quickly identifying false positives to avoid unnecessary escalations.

---

## 🔍 Step-by-Step: False Positive Triage Process

### 1. Understand the Alert Context
- Identify what triggered the alert (e.g., rule ID, correlation logic).
- Check for associated MITRE ATT&CK techniques.
- Determine the system or asset that generated the alert.

> **Example**: Alert from Wazuh Rule ID 92021 – suspicious user-agent string in HTTP header.

---

### 2. Correlate with Known Baselines
- Compare behavior to normal operational baselines.
- Look for whitelisted users, applications, or services.

> **Example**: A scheduled Nessus scan generates multiple Nmap detections.

---

### 3. Review Logs for Supporting Evidence
- Analyze endpoint logs (e.g., Sysmon, Windows Event Logs).
- Review network logs (e.g., firewall, DNS, proxy).
- Examine parent-child process relationships.

---

### 4. Validate Asset Role
- Determine if the asset (server, workstation, endpoint) is performing its expected function.
- Consider if the behavior aligns with that function.

---

### 5. Cross-check with Threat Intelligence
- Look up associated IPs, domains, or hashes in threat intelligence platforms.
- Validate if the activity matches a known malicious indicator.

---

### 6. User Activity Verification
- Confirm if the activity was initiated by a legitimate user.
- Check for authorized administrative or IT activity.

---

### 7. Review Historical Alerts
- Has this alert appeared before?
- Was it previously triaged as a false or true positive?

---

##  Sample Triage Decision Table

| Indicator              | Observed Behavior                              | Verdict         |
|------------------------|--------------------------------------------------|-----------------|
| Source IP              | Internal vulnerability scanner                 | False Positive  |
| File hash              | Matches internal software install              | False Positive  |
| PowerShell command     | User-initiated installation                    | False Positive  |
| DNS query              | Known malicious domain in threat feeds         | True Positive   |
| Process parent         | Spawned from `explorer.exe` (non-suspicious)   | False Positive  |

---

##  Tips for Reducing False Positives

- Tune SIEM rules with known exclusions.
- Regularly update behavioral baselines.
- Create allowlists for trusted assets and applications.
- Document all known-good behaviors and approved tasks.

---

##  Summary
Identifying false positives is essential to ensure efficient use of SOC resources. SOC 1 Analysts must rely on log correlation, baseline knowledge, asset context, and threat intelligence to make informed triage decisions.

