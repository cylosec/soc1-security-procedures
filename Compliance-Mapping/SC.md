# NIST 800-53 Control Family: SC – System and Communications Protection

## Summary
Ensures secure communication, data integrity, and protection from external and internal threats.

## ISO/IEC 27001 Mapping
- **A.8.20** – Secure network services
- **A.8.21** – Use of cryptography

## SOX Relevance
- **Section 404**: Controls over transmission and access to financial data

## SOC 1–2 Analyst Action Items
- Monitor for unencrypted traffic (e.g., HTTP, FTP)
- Detect data exfiltration attempts
- Ensure VPN, TLS, and email encryption are enforced

## Detection/Audit Examples
- Alert on outbound traffic to high-risk IPs
- IDS detection of insecure protocols
- Email DLP violation alerts
