# NIST 800-53 Control Family: AU – Audit and Accountability

## Summary
Tracks user activities and ensures logs are collected, protected, and analyzed to detect unauthorized behavior.

## ISO/IEC 27001 Mapping
- **A.8.15** – Logging
- **A.8.16** – Monitoring activities
- **A.8.12** – Event logging

## SOX Relevance
- **Section 404**: Requires audit trails and evidence for internal controls over financial reporting.

## SOC 1–2 Analyst Action Items
- Monitor log ingestion across endpoints and servers
- Detect gaps or corruption in logs
- Alert on high-value activity (e.g., permission changes)
- Retain logs per compliance policy (e.g., 90 days searchable)

## Detection/Audit Examples
- SIEM alert: Sysmon ID 4625 (failed login attempt)
- Review for gaps or anomalies in log timestamps
- Validate Wazuh agent log collection across systems
