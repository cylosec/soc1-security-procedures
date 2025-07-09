# NIST 800-53 Control Family: SI – System and Information Integrity

## Summary
Monitors systems to detect and respond to malicious activity, unauthorized changes, and data integrity issues.

## ISO/IEC 27001 Mapping
- **A.8.7** – Protection against malware
- **A.8.8** – Management of technical vulnerabilities

## SOX Relevance
- **Section 404**: Focuses on integrity of financial systems and logs

## SOC 1–2 Analyst Action Items
- Monitor for malware alerts, hash anomalies, and unauthorized software
- Correlate EDR data with SIEM alerts
- Investigate suspicious DNS queries or beaconing behavior

## Detection/Audit Examples
- Wazuh malware alert mapped to VirusTotal hash
- Sysmon ID 7: New process image loaded
- DNS tunneling attempt detected via traffic anomalies

