# NIST 800-53 Overview for SOC 1

## Objective
To align SOC 1 monitoring and control checks with NIST 800-53 security and privacy controls.

## Key Control Families

| Control ID | Name                      | Relevance                        |
|------------|---------------------------|----------------------------------|
| AC-2       | Account Management        | Review of user provisioning logs |
| AU-6       | Audit Review, Analysis    | Log correlation and SIEM alerts  |
| SC-7       | Boundary Protection       | Firewall/IDS monitoring          |
| IR-4       | Incident Handling         | Response to critical alerts      |

## Sample Mapping
> **Example:** A failed login brute-force alert could be mapped to:
- **AC-7:** Unsuccessful login attempts
- **AU-14:** Session audit capability
