---
title: "Compliance Cheat Sheet for SOC 1 Analysts"
date: 2025-07-06
author: "SOC Team"
category: "Cheat Sheets"
tags: [Compliance, NIST-800-53, ISO-27001, PCI-DSS, HIPAA, SOC1]
layout: post
---

#  Compliance Cheat Sheet for SOC 1 Analysts

This quick reference maps core responsibilities in a SOC 1 environment to regulatory controls from NIST 800-53, ISO/IEC 27001, PCI-DSS, and HIPAA.

---

##  Access Control & Identity Management

| Area                        | NIST 800-53           | ISO 27001       | PCI-DSS v4.0       | HIPAA             |
|-----------------------------|------------------------|------------------|---------------------|--------------------|
| User Account Provisioning   | AC-2, AC-5             | A.9.2            | 7.1.2               | 164.308(a)(3)      |
| Least Privilege             | AC-6                  | A.9.1.2          | 7.2.3               | 164.308(a)(4)      |
| Session Timeout             | AC-12                 | A.9.4.2          | 8.2.8               | 164.312(a)(2)(iii) |
| MFA for Admin Access        | IA-2(1), IA-5(11)     | A.9.4.3          | 8.4.2               | 164.312(d)         |

---

##  Logging, Monitoring & SIEM Correlation

| Area                        | NIST 800-53           | ISO 27001       | PCI-DSS v4.0       | HIPAA             |
|-----------------------------|------------------------|------------------|---------------------|--------------------|
| Security Log Collection     | AU-2, AU-6             | A.12.4           | 10.2.1              | 164.312(b)         |
| Log Retention               | AU-11                 | A.12.4.1         | 10.5.1              | 164.316(b)(2)(i)   |
| Audit Log Review            | AU-6(1), AU-6(3)      | A.12.7.1         | 10.6.1              | 164.308(a)(1)(ii)(D)|
| Anomaly Detection / Alerts  | SI-4                  | A.12.6.1         | 10.7.1              | 164.308(a)(6)(ii)  |

---

##  Vulnerability & Risk Management

| Area                        | NIST 800-53           | ISO 27001       | PCI-DSS v4.0       | HIPAA             |
|-----------------------------|------------------------|------------------|---------------------|--------------------|
| Risk Assessment             | RA-3, RA-5             | A.8.2, A.15      | 12.2.1              | 164.308(a)(1)(ii)(A) |
| Vulnerability Scanning      | RA-5, SI-2             | A.12.6.1         | 11.3.1, 11.3.2      | 164.308(a)(1)(ii)(A) |
| Patch Management            | SI-2, CM-3             | A.12.6.1         | 6.3.3               | 164.308(a)(8)      |
| Configuration Baselines     | CM-2, CM-6             | A.9.4.5          | 2.2                 | 164.310(d)(1)      |

---

##  Incident Response & Escalation

| Area                        | NIST 800-53           | ISO 27001       | PCI-DSS v4.0       | HIPAA             |
|-----------------------------|------------------------|------------------|---------------------|--------------------|
| Incident Response Plan      | IR-1, IR-4, IR-6       | A.16.1           | 12.10.1             | 164.308(a)(6)      |
| Escalation Procedures       | IR-4, IR-5             | A.16.1.4         | 12.10.5             | 164.308(a)(6)(ii)  |
| Retaining Incident Records  | IR-6(1), AU-11         | A.16.1.7         | 12.10.6             | 164.308(a)(7)(ii)(B) |
| Post-Incident Review        | IR-4(1), IR-8          | A.16.1.6         | 12.10.7             | 164.308(a)(6)(ii)  |

---

##  Documentation & Compliance Reporting

| Area                        | NIST 800-53           | ISO 27001       | PCI-DSS v4.0       | HIPAA             |
|-----------------------------|------------------------|------------------|---------------------|--------------------|
| Policy Documentation        | PL-1, PL-2             | A.5.1            | 12.1.1              | 164.316(a)         |
| Evidence for Audits         | CA-7, AU-12            | A.18.1.3         | 12.11.2             | 164.312(b), 164.316 |
| Internal Controls Testing   | CA-2, CA-5             | A.9, A.12.1      | 12.11               | 164.308(a)(8)      |
| Control Effectiveness Logs  | CA-7, AU-6             | A.18.2.3         | 10.2.7              | 164.308(a)(1)(ii)(D)|

---

##  SOC 1 Analyst Tips

- **Tag tickets** based on regulation affected (e.g., `HIPAA`, `PCI`, `SOX`).
- **Use SIEM dashboards** to track compliance control coverage.
- **Log reviews and escalations** should reference specific control IDs when possible.
- **Maintain audit-readiness** by documenting ticket resolutions with timestamps, evidence, and alert metadata.

---

