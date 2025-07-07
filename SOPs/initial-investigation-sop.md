# Initial Investigation SOP

**Role:** SOC Level 1 Analyst  
**Purpose:** To provide a repeatable and documented procedure for conducting initial investigations in response to SIEM alerts or suspicious activity.

---

## 1. Alert Intake

- Receive alert via SIEM (e.g., Wazuh).
- Check alert severity and classification (Critical, High, Medium, Low).
- Verify alert source:
  - Hostname  
  - IP address  
  - Agent name  
  - Timestamp

---

## 2. Alert Correlation

- Review associated MITRE ATT&CK ID or Rule ID (e.g., `92021`, `sysmon_event1`, etc.)
- Identify process names, command lines, parent-child relationships (for EDR/Sysmon data)
- Cross-reference:
  - Known-good processes or hashes (allowlist)
  - VirusTotal, AbuseIPDB, Hybrid Analysis, or internal threat intel
- Note any user activity tied to the alert (especially if triggered via user behavior)

---

## 3. Triage & Log Review

- Pull related log entries before and after the alert timestamp (±5 mins or more if needed)
- Check for:
  - Login attempts  
  - File modifications  
  - Registry changes  
  - Network connections  
  - Repeated behavior or previous alerts from the same host/IP

---

## 4. Baseline Assessment

- Determine if behavior is expected:
  - Was the alert triggered during working hours?
  - Is the process part of routine software or admin tools?
  - Is the source user account privileged or service-based?

---

## 5. Initial Determination

- **Benign** — Document reasoning (e.g., scheduled task, known IT software)
- **Suspicious** — Flag for escalation (SOC 2 or IR team)
- **Malicious** — Trigger escalation protocol immediately

---

## 6. Ticket Documentation

- Create or update a ticket with:
  - Alert name and rule ID
  - Affected host/user/IP
  - Summary of log findings
  - Enrichment results (e.g., VirusTotal link, MITRE ID)
  - Triage determination (Benign / Suspicious / Malicious)
  - Next recommended steps (monitor, escalate, isolate, etc.)

---

## 7. Containment (if authorized)

*(Optional if part of SOC 1 duties in this environment)*

- Disable affected user account  
- Quarantine host (if EDR allows)  
- Notify SOC Tier 2 or Incident Response

---

## 8. Close or Escalate

- **If resolved:**
  - Mark as closed with full documentation.
  - Add to Lessons Learned or Alert Tuning list if applicable.

- **If escalation required:**
  - Notify assigned SOC 2 or Incident Handler
  - Attach logs, enrichment, and timeline to assist with investigation
