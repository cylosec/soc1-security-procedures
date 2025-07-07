# SOC 1 Analyst Daily Workflow – Standard Operating Procedure

## Purpose
This SOP outlines the daily responsibilities and standardized workflow of a SOC 1 Analyst to ensure effective security monitoring, triage, documentation, and compliance with regulatory standards (e.g., SOX, ISO 27001, NIST 800-53).

---

## 1. Start of Shift: Environment Validation
- Log into all relevant platforms (SIEM, endpoint detection, ticketing system).
- Confirm endpoint visibility and agent heartbeat status (e.g., Wazuh, OSSEC).
- Validate log ingestion from critical assets (Domain Controllers, firewalls, servers).

---

## 2. Review Overnight Alerts and Escalations
- Open the ticketing system (Jira, ServiceNow) and filter for:
  - Unresolved critical or high severity alerts
  - Escalated tickets from the previous shift
  - Tickets nearing SLA thresholds
- Take ownership of appropriate investigations based on severity and expertise.

---

## 3. Monitor SIEM and Real-Time Alerts
- Continuously monitor real-time dashboards for:
  - Malware activity
  - Unauthorized login attempts
  - Policy violations
  - Privilege escalation
  - Abnormal script execution (e.g., PowerShell, Bash)

---

## 4. Alert Triage and Classification
- Investigate new alerts by gathering:
  - Source IP, hostname, user account, process name
  - Event logs and supporting evidence (Sysmon, Windows Event Viewer, Linux syslog)
- Classify the alert as:
  - True Positive (TP)
  - False Positive (FP)
  - Informational/Benign (INF)

---

## 5. Response and Ticket Documentation
- Log all actions in the ticketing system, including:
  - Summary of the alert
  - Investigation findings
  - Analyst actions and observations
  - Containment or remediation recommendations
- Tag tickets with MITRE ATT&CK IDs (e.g., T1059 for command-line execution)

---

## 6. Threat Intelligence Correlation
- Check suspicious IPs, hashes, and domains using:
  - Open Threat Exchange (OTX)
  - AbuseIPDB
  - VirusTotal
- Update ticket with threat intel findings and escalate if necessary.

---

## 7. Log and Compliance Checks
- Ensure log collection and retention policies are being met:
  - Example: 90-day searchable logs, 1-year archival
- Check compliance on critical endpoints for:
  - Time synchronization
  - Tamper protection
  - Logging agent status

---

## 8. Shift Handoff and Collaboration
- Prepare shift summary:
  - Ongoing investigations
  - Resolved incidents
  - Escalated cases
  - New detection rules deployed or suppressed
- Participate in handover brief or daily stand-up meetings.

---

## 9. Update Documentation and Knowledge Base
- Add new procedures, tuning steps, or investigative findings to:
  - Internal runbooks
  - Team Wiki or Confluence
  - Markdown-based GitHub knowledge base

---

## 10. Continuous Improvement
- Review SIEM rule logic for:
  - False positive reduction
  - Detection enhancement
- Participate in tabletop exercises or red/blue team scenarios if scheduled.
- Stay current with emerging threats and CVEs relevant to the monitored environment.

---

## Version Control
- **Last updated:** July 6, 2025
- **Maintainer:** SOC1 Security Operations Team

