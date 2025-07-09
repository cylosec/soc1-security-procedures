# NIST 800-53 Control Family: AC – Access Control

## Summary
Access Control (AC) focuses on limiting information system access to authorized users, processes, and devices. It ensures least privilege and appropriate separation of duties.

## ISO/IEC 27001 Mapping
- **A.5.15** – Access control
- **A.5.16** – Identity management
- **A.5.17** – Authentication

## SOX Relevance
- **Section 404**: Verifies that access to financial data is restricted, logged, and reviewed.
- **Key focus**: User account reviews, admin group access, and privileged account monitoring.

## SOC 1–2 Analyst Action Items
- Monitor privileged account activity (e.g., Domain Admins)
- Alert on new account creation or privilege escalation
- Review login logs and group membership changes
- Verify access rights for users during audits

## Detection/Audit Examples
- **Wazuh Rule**: Alert when a user is added to the `Administrators` group
- **Sysmon ID 4720**: A user account was created
- **Periodic Audit**: Run AD group membership reports and compare against baseline

## Sample Command (PowerShell)
```powershell
Get-ADGroupMember -Identity "Domain Admins"
