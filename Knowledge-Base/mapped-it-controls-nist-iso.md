# IT Controls Mapped to NIST 800-53 & ISO/IEC 27001

This document provides a high-level mapping between common IT Controls and the corresponding control families from two major frameworks: **NIST 800-53 Rev. 5** and **ISO/IEC 27001:2022 Annex A**.

---

## General IT Controls (GITCs)

| IT Control Area         | Description                                                                 | NIST 800-53 Control Families                  | ISO 27001:2022 Controls (Annex A)         |
|--------------------------|-----------------------------------------------------------------------------|-----------------------------------------------|-------------------------------------------|
| Access Controls          | Enforcing role-based access, MFA, least privilege                         | AC - Access Control, IA - Identification & Authentication | A.5.15, A.5.18, A.8.2                     |
| Change Management        | Controlling changes to systems, applications, configurations               | CM - Configuration Management, SA - System & Services Acquisition | A.8.32, A.8.33, A.8.9                     |
| Backup and Recovery      | Ensuring critical data is backed up and restorable                        | CP - Contingency Planning, SI - System & Info Integrity | A.8.13, A.8.23, A.5.30                    |
| Incident Management      | Detection, response, documentation, and resolution of security events     | IR - Incident Response                        | A.5.24, A.5.25, A.5.28                    |
| System Development Life Cycle (SDLC) | Controls for secure application development and release              | SA - System & Services Acquisition, PL - Planning | A.8.25, A.8.26, A.8.28                    |

---

## Application Controls

| Control Type       | Description                                                  | NIST 800-53                                | ISO 27001:2022                            |
|--------------------|--------------------------------------------------------------|---------------------------------------------|-------------------------------------------|
| Input Controls     | Validate data entry and enforce constraints                 | SI-10, AU-6, AC-3                           | A.8.23, A.8.24, A.5.8                      |
| Processing Controls| Ensure accuracy, completeness, and integrity of operations  | SI-7, AU-3, AC-6                            | A.8.11, A.8.23                             |
| Output Controls    | Ensure output data integrity, protection, and distribution  | SC-12, SC-28                                | A.5.15, A.8.27                             |
| Integrity Checks   | Enforce business logic and prevent corruption               | SI-7, SC-12                                 | A.8.7, A.8.11                              |

---

## Functional Control Types

| Control Type    | Description                                   | NIST 800-53 Examples         | ISO 27001:2022 Examples      |
|-----------------|-----------------------------------------------|-------------------------------|-------------------------------|
| Preventive      | Avoid errors or threats before they occur     | AC-2, SC-7, CM-2              | A.5.15, A.8.4, A.8.9          |
| Detective       | Identify incidents or anomalies               | AU-6, IR-4, SI-4              | A.5.25, A.5.17, A.8.16        |
| Corrective      | Remediate and recover from incidents          | CP-2, IR-5, SI-2              | A.5.28, A.8.13, A.8.14        |
| Compensating    | Alternate controls when standard controls aren't feasible | PL-2, CA-2                   | A.5.5, A.5.8, A.8.35          |

---

## Notes

- This is a simplified crosswalk for educational and planning purposes.
- Specific mappings depend on organizational context and risk appetite.
- SOC 1 audits may only focus on controls relevant to financial reporting, but aligning with NIST/ISO helps ensure broader compliance maturity.

---

## Related Files

- [IT Controls Overview](./it-controls.md)
- [Compliance SOP](./compliance-soc1.md)
- [SOC 1 GRC Procedures](./soc1-grc-sop.md)

---

**Version:** 1.0  
**Maintainer:** SOC 1 GRC & Security Operations Team  
