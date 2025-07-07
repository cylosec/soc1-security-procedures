---
title: "SOC Compliance Cheat Sheet with Overview"
date: 2025-07-06
author: "SOC Team"
category: "Cheat Sheets"
tags: [SOC1, SOC2, Compliance, GRC, InternalControls]
layout: post
---

# SOC Compliance Cheat Sheet

This cheat sheet provides a practical summary of key SOC (System and Organization Controls) compliance concepts relevant to SOC 1 and SOC 2 environments. It focuses on audit readiness, control monitoring, and analyst responsibilities within a Security Operations Center (SOC).

---

## Overview of SOC Compliance

**SOC 1:**  
Focused on internal controls over financial reporting (ICFR). Commonly required by organizations providing services that affect the financial statements of their clients. Audits are performed under the **SSAE 18** standard.

**SOC 2:**  
Focused on controls related to **security, availability, processing integrity, confidentiality**, and **privacy**. Based on the **AICPA Trust Services Criteria (TSC)**. Essential for tech and cloud service providers.

**SOC 3:**  
Similar to SOC 2 but intended for general public use. Does not contain the same level of detail.

---

## SOC 1 vs. SOC 2 – Key Differences

| Feature/Focus               | SOC 1                                | SOC 2                                 |
|----------------------------|--------------------------------------|----------------------------------------|
| Primary Audience           | Auditors, regulators, financial depts | Customers, partners, internal teams   |
| Framework                  | SSAE 18 (AT-C 320)                    | Trust Services Criteria (TSC)         |
| Controls Type              | ICFR-focused                          | Security & privacy-focused            |
| Report Types               | Type I and Type II                    | Type I and Type II                    |
| Example Controls           | User access to financial systems      | Incident response, encryption, logging|

---

## SOC Analyst Responsibilities Under SOC 1 and SOC 2

| Responsibility                    | SOC 1 Relevance                          | SOC 2 Relevance                             |
|----------------------------------|------------------------------------------|---------------------------------------------|
| Log and Alert Monitoring         | Validate access control logs (ICFR)      | Detect security incidents in real time      |
| Ticketing and Documentation      | Provide audit trails for incident handling | Track response actions to incidents         |
| Privilege Escalation Detection   | Identify unauthorized access to financial systems | Enforce least privilege and review access   |
| Change Management Review         | Validate system changes tied to financial reporting | Confirm security implications of changes    |
| Vulnerability Management         | Ensure financial-impacting systems are patched | Track all high-severity vulnerabilities     |

---

## Sample Control Areas (SOC 2 Trust Services Criteria)

| Category              | Example Control Objectives                              |
|-----------------------|----------------------------------------------------------|
| Security              | Firewall rules, MFA, IDS alerts                          |
| Availability          | System uptime monitoring, disaster recovery tests        |
| Processing Integrity  | Data validation checks, process automation logs          |
| Confidentiality       | Data encryption, DLP monitoring                          |
| Privacy               | Consent management, PII data handling procedures         |

---

## SOC Compliance Best Practices

- Implement log retention per policy (e.g., 90 days searchable, 1 year archived)
- Use SIEM tools (e.g., Wazuh, Splunk) to enforce alert correlation and escalation paths
- Document all investigations with timestamps and analyst notes
- Regularly review privileged accounts and group memberships
- Participate in quarterly control effectiveness reviews and risk assessments
- Maintain evidence (screenshots, reports, ticket logs) for audit readiness

---

## Audit Prep and Reporting

| Task                          | Description                                              |
|-------------------------------|----------------------------------------------------------|
| Control Testing               | Assist in periodic testing of internal controls          |
| Evidence Collection           | Provide proof of alert review, log monitoring, response  |
| Exception Handling            | Document root cause and remediation of non-compliant findings |
| Collaboration with GRC Team  | Align technical logs with control narratives             |

---

## Resources

- AICPA: SOC Reports Overview – https://www.aicpa.org
- SSAE 18 Guidance – https://www.ssae-18.com
- Trust Services Criteria – https://www.aicpa.org/interestareas/frc/assuranceadvisoryservices/trust-services-criteria.html

