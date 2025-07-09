#  NIST 800-53 → ISO 27001 → SOX Mapping

This file maps key NIST SP 800-53 control families to their equivalent ISO/IEC 27001 controls and indicates their relevance to SOX (Sarbanes-Oxley Act) compliance. It's designed to help SOC 1–2 Analysts understand the intersection of technical monitoring, compliance obligations, and audit readiness.

---

##  Mapping Table

| NIST 800-53 ID | Control Family               | ISO 27001:2022 Control (Annex A) | SOX Relevance | Analyst Notes                                                  |
|----------------|------------------------------|---------------------------|----------------|-----------------------------------------------------------------|
| AC             | Access Control               | A.5.15, A.5.16, A.5.17     | ✅ Critical     | User provisioning, least privilege, account disablement logs   |
| AT             | Awareness and Training       | A.6.3                      | ✅ Yes          | Track user training completions and phishing simulations       |
| AU             | Audit and Accountability     | A.8.15, A.8.16, A.8.12     | ✅ Core         | Enable audit logs, validate log integrity (Sysmon/Wazuh)       |
| CA             | Security Assessments         | A.5.30, A.5.33             | ✅ Yes          | Provide audit evidence, report compliance gaps                 |
| CM             | Configuration Management     | A.8.9, A.8.10              | ✅ Key          | Monitor file integrity, detect unauthorized changes (FIM)      |
| CP             | Contingency Planning         | A.5.29, A.5.30             | ⛔ Limited      | Ensure backups exist; test recovery scenarios periodically     |
| IA             | Identification & Authentication | A.5.17, A.5.18          | ✅ Core         | MFA, lockouts, privileged account activity                     |
| IR             | Incident Response            | A.5.24, A.5.25             | ✅ Required     | Document and escalate incidents; test IR plan annually         |
| MA             | Maintenance                  | A.8.23, A.8.24             | ❌ Rare         | Rarely applicable unless endpoint forensics are involved       |
| MP             | Media Protection             | A.8.10, A.8.11             | ❌ No           | Minimal relevance for digital-only SOC teams                   |
| PE             | Physical Security            | A.7.4                      | ❌ No           | Managed by facilities; not SOC team responsibility             |
| PL             | Planning                     | A.5.1                      | ✅ Optional     | Align SOC procedures with org-wide security plans              |
| PS             | Personnel Security           | A.6.1                      | ✅ Yes          | Background checks, insider threat alerts                       |
| RA             | Risk Assessment              | A.5.4, A.5.5               | ✅ Required     | Support vulnerability risk scoring, prioritization             |
| SA             | System Acquisition           | A.5.10                     | ✅ Some         | Align SOC logging and alerts with new app deployments          |
| SC             | Systems/Comm Protection      | A.8.20, A.8.21             | ✅ Core         | Detect unencrypted protocols, DLP policies                     |
| SI             | System & Info Integrity      | A.8.7, A.8.8               | ✅ Critical     | Antivirus alerts, anomaly detection, malware triage            |

---

##  SOX Key Sections for Security Analysts

| SOX Section | Title                                   | Security Implication                        |
|-------------|------------------------------------------|----------------------------------------------|
| 302         | Corporate Responsibility for Reporting   | Security event disclosures by management     |
| 404         | Management Assessment of Internal Controls | Access logs, change control, system monitoring |
| 802         | Criminal Penalties for Record Falsification | Log tampering, audit trails, alert evidence retention |

---

##  Analyst Action Items

- **Correlate alerts** to NIST/ISO controls when triaging incidents  
- **Document IR workflows** with SOX Section 404 in mind  
- **Log all privileged actions** (especially in finance or ERP systems)  
- **Validate alerts** map to business risk and compliance standards  
- **Provide control evidence** to internal/external auditors using this mapping

---

##  Suggested GitHub Path


---

##  References

- NIST SP 800-53 Rev. 5: https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final  
- ISO/IEC 27001:2022 Standard: https://www.iso.org/standard/82875.html  
- SOX Law Summary: https://www.soxlaw.com/

