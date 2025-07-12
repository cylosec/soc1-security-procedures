# True Positive vs False Positive Cheat Sheet

## Understanding the Difference

| Term              | Definition                                                    |
|-------------------|---------------------------------------------------------------|
| True Positive (TP) | The alert correctly identifies malicious or unauthorized activity. |
| False Positive (FP)| The alert is triggered by legitimate behavior mistakenly identified as malicious. |

---

## Quick Checklist for Determining False Positive

| Check                     | Description                                                              | Result |
|---------------------------|--------------------------------------------------------------------------|--------|
| Contextual Review         | Is the behavior expected for this user/system (e.g., scheduled script)?  | [ ]    |
| User Validation           | Is the user who triggered the event authorized (e.g., domain admin)?     | [ ]    |
| Source & Destination      | Are the source IP or destination domains trusted/internal?               | [ ]    |
| Command or File Path      | Is the script or binary part of a known maintenance task?                | [ ]    |
| Timing                    | Did the event occur during business hours or change window?              | [ ]    |
| System Role               | Is this system intended to run such tasks (e.g., backup server)?         | [ ]    |
| Documentation Exists?     | Is this action/script listed in onboarding or IT SOPs?                   | [ ]    |
| Repetition Pattern        | Does this alert trigger frequently with no signs of compromise?          | [ ]    |
| Impact Assessment         | No indicators of persistence, lateral movement, or data exfiltration?    | [ ]    |
| Sandbox/Testing Outcome   | Benign if tested in isolated environment?                                | [ ]    |

**Recommendation**:  
If 6 or more boxes are checked with no other threat indicators, it is likely a False Positive.

---

## Quick Checklist for Confirming True Positive

| Check                     | Description                                                              | Result |
|---------------------------|--------------------------------------------------------------------------|--------|
| Unusual Command or Binary | Is the process uncommon or obfuscated (e.g., PowerShell base64)?         | [ ]    |
| Unauthorized Access       | Access attempt from unknown or suspicious account/IP?                    | [ ]    |
| Privilege Escalation      | Signs of attempts to elevate privileges?                                 | [ ]    |
| Process Chain Anomaly     | Suspicious parent-child process relationship?                            | [ ]    |
| External Communication    | Contact to known malicious IPs/domains? (Check threat intel)             | [ ]    |
| Persistence Mechanism     | Registry, startup folder, scheduled task creation?                       | [ ]    |
| Defense Evasion           | Event logs cleared, antivirus disabled, etc.?                            | [ ]    |
| File Dropper/Loader       | Malware payloads detected or dropped files with high entropy?            | [ ]    |
| User Interaction          | Triggered via phishing email or suspicious web activity?                 | [ ]    |
| MITRE Mapping             | Can the activity be tied to a known TTP (e.g., T1059 – Command Line)?    | [ ]    |

**Recommendation**:  
If 4 or more boxes are checked and correlated with IOC data, treat as a True Positive and escalate.

---

## Example: False Positive Report

### Context & Baseline Check

The PowerShell script observed is part of the routine onboarding tasks executed by IT admins. It performs software installation and registry edits.

**Verdict**: False Positive  
- Run by: Domain Admin  
- Script location: Trusted network share  
- Frequency: Once per new user creation  
- No anomalous behavior or IOC found

**Recommendation**:  
- Suppress alert for this path/script when executed by trusted admins.  
- Document in SOC Knowledge Base.

---

## Example: True Positive Report

### Alert Summary

- Process: `powershell.exe` (EncodedCommand)  
- Parent: `winword.exe`  
- User: Standard domain user (not admin)  
- Destination IP: `185.199.111.153` (Flagged by threat intel)

**Verdict**: True Positive  
- Behavior: Obfuscated PowerShell payload post email attachment  
- Lateral movement indicators found (e.g., WMI activity)  
- No IT documentation for this action

**Recommendation**:  
- Isolate host immediately  
- Escalate to Incident Response  
- Conduct deeper forensic analysis  
- Review affected user's email and web activity


