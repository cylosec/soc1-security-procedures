#  NIST SP 800-53 Control Families Cheat Sheet for SOC 1–2 Analysts

##  Full List of NIST 800-53 Control Families (Rev. 5)

1. AC – Access Control  
2. AT – Awareness and Training  
3. AU – Audit and Accountability  
4. CA – Security Assessment and Authorization  
5. CM – Configuration Management  
6. CP – Contingency Planning  
7. IA – Identification and Authentication  
8. IR – Incident Response  
9. MA – Maintenance  
10. MP – Media Protection  
11. PE – Physical and Environmental Protection  
12. PL – Planning  
13. PS – Personnel Security  
14. RA – Risk Assessment  
15. SA – System and Services Acquisition  
16. SC – System and Communications Protection  
17. SI – System and Information Integrity  
18. SR – Supply Chain Risk Management  
19. PM – Program Management  
20. PT – Privacy Controls (mapped from NIST SP 800-37/800-122)

---

##  SOC 1–2 Analyst Control Mapping Table

| Control ID | Control Family               | SOC 1–2 Analyst Relevance                              | Common Tasks / Examples                                         | ISO 27001 Mapping | SOX Relevance |
|------------|------------------------------|--------------------------------------------------------|------------------------------------------------------------------|-------------------|----------------|
| **AC**     | Access Control               | Monitor and report on user permissions and logins      | Least privilege, MFA enforcement, group policy checks            | A.9               | ✔️ User access reviews |
| **AT**     | Awareness and Training       | Track user security training, phishing tests           | Simulated phishing reports, user compliance tracking             | A.7.2.2           | ✔️ Training documentation |
| **AU**     | Audit and Accountability     | SIEM log correlation, audit trail maintenance          | Sysmon logging, audit log integrity, failed login reports        | A.12.4            | ✔️ Financial data access logging |
| **CA**     | Security Assessment          | Support audits, document control implementation        | Audit readiness reports, GRC support                            | A.18.2            | ✔️ Internal controls testing |
| **CM**     | Configuration Management     | Detect unauthorized changes, config baseline alerts    | File Integrity Monitoring (FIM), registry monitoring             | A.12.1            | ✔️ Configuration control evidence |
| **CP**     | Contingency Planning         | Monitor backup alerts and DR testing logs              | Backup failures, ransomware recovery procedures                  | A.17              | ❌ (minimal)   |
| **IA**     | Identification & Authentication | Detect and respond to login anomalies               | Brute-force alerts, password policies, lockouts                  | A.9.4             | ✔️ Access to financial data |
| **IR**     | Incident Response            | Triage alerts, document incidents, escalate if needed  | JIRA tickets, playbook execution, MITRE TTP tagging              | A.16              | ✔️ Breach reporting |
| **RA**     | Risk Assessment              | Support vulnerability assessments, prioritize findings | Risk scoring, CVE analysis, remediation ticketing                | A.8.2             | ✔️ Risk mitigation planning |
| **SC**     | System & Communications Protection | Detect insecure traffic and protect data           | Cleartext detection, endpoint encryption status, network scans   | A.13              | ✔️ System security controls |
| **SI**     | System & Information Integrity | Identify malware, data corruption, unauthorized changes | Antivirus alerts, EDR correlation, DNS anomalies                 | A.12.2            | ✔️ SOX 404 control testing |

---

##  Compliance Framework Mapping Key

- **ISO/IEC 27001**: International standard for Information Security Management Systems (ISMS)  
- **SOX**: Sarbanes-Oxley Act – U.S. law requiring financial data integrity, internal controls, and audit transparency  
  - SOC 1 reports often include controls relevant to SOX Section 404

---

##  Usage in SOC Environments

SOC 1–2 Analysts should use this cheat sheet to:

- Understand how their responsibilities align with NIST, ISO, and SOX requirements
- Justify detection rules and alert responses during audits
- Support compliance evidence collection for internal and external auditors
- Map SIEM tuning and security procedures to control families and real-world frameworks

---



