# NIST 800-53 Control Family: IA – Identification and Authentication

## Summary
Controls around verifying identities of users, processes, and devices before access is granted.

## ISO/IEC 27001 Mapping
- **A.5.17** – Authentication
- **A.5.18** – Use of secret authentication information

## SOX Relevance
- **Section 404**: Ensures systems handling financial data are protected by secure authentication

## SOC 1–2 Analyst Action Items
- Alert on failed logins, lockouts, and brute-force attempts
- Monitor use of privileged accounts
- Verify MFA enforcement on key systems

## Detection/Audit Examples
- Sysmon ID 4625: Failed login attempt
- SIEM correlation of repeated login failures from same IP
- MFA failure logs from Azure AD or Okta
