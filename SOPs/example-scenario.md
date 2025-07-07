# Example Scenario – T1059 Command and Scripting Interpreter Alert (Critical Severity)

## Scenario Overview

**Date/Time:** 2025-07-06 14:23 EST  
**Severity Level:** 14 (Critical)  
**MITRE ATT&CK ID:** T1059 – Command and Scripting Interpreter  
**Source:** Wazuh Alert (Sysmon Event ID 1 – Process Creation)  
**Target Host:** WIN-DC01.cylosec.local  
**Username:** svc_backup  
**Process Path:** `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe`  
**Command Line:** `powershell.exe -nop -w hidden -EncodedCommand JAB...`  

---

## Step 1 – Triage and Detection

- Detected suspicious PowerShell activity from a service account on a domain controller
- The command line was obfuscated using `-EncodedCommand`, commonly associated with malware or post-exploitation frameworks
- Alert triggered from Wazuh rule ID `92041` (Custom Command Execution with Encoded String)
- Mapped to MITRE Technique: **T1059.001 – PowerShell**

---

## Step 2 – Correlation and Context

- Sysmon logs indicate this PowerShell process was spawned by `svchost.exe`
- No scheduled tasks or authorized scripts were expected at this time
- The account `svc_backup` had no history of PowerShell usage
- Additional alerts indicate failed authentication attempts from the same host

---

## Step 3 – Immediate Actions

- Host `WIN-DC01.cylosec.local` isolated from the network via EDR
- Blocked IOC hash from PowerShell script at firewall and EDR level
- Notified SOC 2 and escalated to Incident Response team

---

## Step 4 – Investigation and Evidence Collection

- Pulled full process tree from Sysmon logs (Wazuh/OpenSearch)
- Collected:
  - Memory dump of host (via Velociraptor)
  - PowerShell logs from Event ID 4104 (Script Block Logging)
  - Domain controller security logs
- Verified encoded command was a Meterpreter stager script (C2 attempt)

---

## Step 5 – Resolution and Documentation

- Host was reimaged, service account `svc_backup` disabled and credentials rotated
- Ticket updated in Jira with full timeline and evidence attachments
- Alert rules tuned to add additional detection for encoded PowerShell commands

---

## MITRE ATT&CK Mapping

| Tactic              | Technique (ID)           | Description                                   |
|---------------------|--------------------------|-----------------------------------------------|
| Execution           | T1059                    | Command and Scripting Interpreter             |
| Execution           | T1059.001                | PowerShell                                    |
| Defense Evasion     | T1027                    | Obfuscated Files or Information               |
| Credential Access   | T1078                    | Valid Accounts (Use of service account)       |
| Command & Control   | T1105                    | Ingress Tool Transfer (encoded payload)       |

---

## Final Notes

- This activity could indicate post-compromise behavior following stolen credentials
- Recommend audit of all service accounts and stricter PowerShell logging across domain-joined machines
- Reported to client’s compliance team as part of SOC 1 reporting obligations
