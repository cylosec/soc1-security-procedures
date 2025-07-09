# False Positive Report: Suspicious PowerShell Activity

## Alert Details

- **Alert Name:** Suspicious PowerShell Command Execution  
- **Rule ID:** Wazuh Rule 92201  
- **Severity:** High  
- **Timestamp:** 2025-07-06 08:17:45 UTC  
- **Host:** WIN-SERVER-DC01.cylosec.local  
- **User:** cylo.admin  
- **Command Detected:**  
  ```powershell
  powershell.exe -ExecutionPolicy Bypass -File \\fileshare\scripts\onboarding.ps1
| Checkpoint                 | Result                                       |
| -------------------------- | -------------------------------------------- |
| Source User                | Verified Active Directory Admin              |
| Host Role                  | Domain Controller (AD Join Operations)       |
| Process Parent             | `explorer.exe` (Normal user interaction)     |
| File Hash / IOC Match      | No known malicious indicators                |
| Threat Intelligence Lookup | Clean – no known bad domains or IPs          |
| Event Correlation          | No lateral movement, no privilege escalation |

## Note

## Context & Baseline Check

This PowerShell script is part of the standard onboarding process used by the IT team. The script installs required software and applies registry settings when new user accounts are provisioned. This behavior is documented and expected.

## Verdict: False Positive

This alert was triggered due to strict PowerShell monitoring rules in the SIEM. However, the command is:

- Run by an authorized IT admin  
- Part of a routine task  
- From a trusted network location  
- With no signs of compromise

## Recommendation

- Suppress alerts for this specific script and command path when executed by domain admins.  
- Document this script and its purpose in the SOC Knowledge Base.  
- Reassess PowerShell alerting thresholds for domain-joined systems used by IT.

## JIRA Ticketing Sample

###  TICKET TYPE: False Positive Review  
**Priority:** Low  
**Status:** Closed  
**Assignee:** SOC Level 1 Analyst  
**Labels:** false-positive, powershell, wazuh, triage-complete

---

##  Alert Summary

**Alert Title:** Suspicious PowerShell Execution  
**SIEM Source:** Wazuh  
**Rule ID:** 92201  
**Severity:** High  
**Date/Time:** 2025-07-06 08:17:45 UTC  
**Hostname:** WIN-SERVER-DC01.cylosec.local  
**User:** cylo.admin  
**Command:**
```powershell
powershell.exe -ExecutionPolicy Bypass -File \\fileshare\scripts\onboarding.ps1

