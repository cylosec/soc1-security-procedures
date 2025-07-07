# SOC 1 Analyst Playbook – Critical and High Impact Alerts

## Purpose
To provide a structured response plan for triaging and responding to high and critical severity alerts, minimizing impact, escalating appropriately, and maintaining audit-ready documentation.

---

## Applicability
This playbook applies to alerts with:
- Rule level 12–15 in Wazuh
- Known malicious indicators (IP, domain, hash)
- Lateral movement attempts
- Unusual privilege escalation or account creation
- Malware, ransomware, or exploit behavior
- Repeated authentication failures or brute-force attempts

---

## Phase 1 – Detection and Triage

### 1. Verify Alert Severity
- Review the Wazuh alert level (12–15 = high/critical)
- Check rule ID and description (e.g., `Sysmon - Suspicious Process Tree`, `MITRE ATT&CK T1055`)

### 2. Identify the Target
- Hostname, IP address, and username involved
- Domain context (e.g., member server vs domain controller)
- Time of event and recurrence

### 3. Correlate Evidence
- Pull additional context from:
  - Sysmon logs (Wazuh or OpenSearch)
  - Authentication logs
  - EDR/XDR dashboard (if integrated)
  - Firewall, DNS, or proxy logs

---

## Phase 2 – Initial Containment

### 4. Isolate the Affected Host (if allowed)
- Quarantine endpoint via EDR, VPN, or network VLAN
- Notify IT/network team if manual isolation is required

### 5. Kill Malicious Process
- Use approved tooling or notify SOC 2 to terminate offending process (via EDR, RMM, or direct command)

### 6. Block IOC
- IPs, domains, hashes (via firewall, proxy, or endpoint blocklists)
- Add to internal watchlist or threat intel feed

---

## Phase 3 – Notification and Escalation

### 7. Create Critical Ticket in Jira (or designated system)
**Title:** `CRITICAL – Suspicious activity on [HOSTNAME] – [ALERT NAME]`  
**Description:**  
- Summary of alert and impact  
- Timestamps and affected systems  
- IOC details (hash, IP, domain, process name)  
- Actions taken: isolation, blocking, etc.  
- Escalation recipient/team

### 8. Notify On-Call/Incident Response
- Notify SOC 2 Lead or IR team by phone/email/chat
- Include full context, ticket ID, and recommendations

---

## Phase 4 – Investigation and Documentation

### 9. Investigate Root Cause
- Was this a real attack or internal misconfiguration?
- Was the threat fully contained?
- Was there data access, exfiltration, or lateral movement?

### 10. Collect Artifacts (if escalated)
- Screenshots of SIEM alerts
- Export logs and full process tree
- Memory dump or forensic image (if permitted)

---

## Phase 5 – Resolution and Lessons Learned

### 11. Finalize Ticket
- Confirm host restored or rebuilt (if needed)
- Add links to supporting documentation or IR report
- Mark ticket as “Resolved” with resolution notes

### 12. Recommend Suppression or Alert Tuning
- If false positive: request rule tuning or suppression
- If true positive: ensure continuous monitoring remains active

### 13. Participate in Post-Incident Review (PIR)
- Contribute to after-action report
- Update SOPs or playbooks if process gaps are found

---

## Checklist – Critical Alert Response

- [ ] Confirm alert severity and affected host
- [ ] Isolate host or terminate process
- [ ] Block IOC or domain
- [ ] Open ticket with all relevant metadata
- [ ] Notify SOC 2 or IR team
- [ ] Investigate root cause
- [ ] Document findings and resolution
- [ ] Update monitoring or suppression rules
