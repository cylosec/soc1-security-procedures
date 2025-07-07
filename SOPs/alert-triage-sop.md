# SOC 1 Analyst – Alert Triage SOP

## Purpose
To provide a structured response workflow for triaging security alerts in the SOC 1 environment, ensuring timely identification, documentation, and escalation of potential security incidents.

---

## Step-by-Step Triage Process

### 1. Alert Intake
- Monitor Wazuh SIEM dashboard for new alerts
- Filter for high-severity or high-priority rules (e.g., rule levels 10–15)
- Confirm alert timestamp and ensure it is current
- Document basic alert details in JIRA or ticketing system

### 2. Initial Assessment
- Review rule ID and rule description (e.g., `Sysmon Event ID 1 - Process Creation`)
- Identify affected asset (Hostname/IP/User)
- Determine alert category (e.g., malware, privilege escalation, brute-force, etc.)
- Correlate with other logs (Sysmon, firewall, authentication, etc.)

### 3. Validate Alert
- Check for false positives (compare to known baselines or routine behavior)
- Review historical logs or alert frequency
- Assess if event is expected (e.g., software update or legitimate admin action)
- Use threat intelligence sources if IP/domain involved

### 4. Classify Severity
- Informational: No action required
- Low: Track, document, and monitor
- Medium: Needs closer review and user/system validation
- High: Potential security incident—prepare for escalation

### 5. Take Immediate Actions (if applicable)
- Isolate host (if policy allows)
- Block IP or hash (via firewall/EDR if permitted)
- Notify team lead or escalate immediately per SOP

### 6. Create/Update Ticket
- Populate with:
  - Alert summary
  - Host/User involved
  - Timestamps
  - Rule ID and severity
  - Screenshot or logs if applicable
  - Action taken (if any)
- Set status: “Under Investigation” → “Escalated” or “Closed – Benign”

### 7. Escalation (if needed)
- Notify SOC 2 or Incident Response team
- Attach evidence: log excerpts, screenshots, IOC details
- Note timeline of events and all actions taken

---

## Daily Checklist for Analysts
- [ ] Review SIEM dashboard regularly
- [ ] Clear/triage alerts with proper documentation
- [ ] Monitor escalated tickets for feedback
- [ ] Check suppression rules for accuracy
- [ ] Collaborate during shift handoff
