# JIRA Incident Ticket Template – Critical Alert

**Summary:**  
`Critical Alert: Unauthorized RDP Access Attempt Detected on WIN-SERVER01`

**Description:**  
A high-priority alert was triggered by Wazuh at `2025-07-06 14:32:11` indicating a brute-force RDP attack against the domain controller.

**Affected Host:** WIN-SERVER01  
**Source IP:** 203.0.113.45  
**Destination Port:** 3389  
**Alert ID:** wazuh-92021  
**Event Source:** Sysmon Event ID 3

**Steps Taken:**
- Reviewed firewall logs (connection allowed)
- Cross-referenced login failures in Event Viewer
- Alert enriched and confirmed via SIEM
- Escalated to Tier 2 SOC for potential incident declaration

**Compliance Reference:**  
- NIST AC-7
- SOC 1: Logical Access Controls
