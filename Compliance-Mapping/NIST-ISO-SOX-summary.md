# NIST 800-53 Control Family Mappings

This folder includes detailed mappings for each relevant NIST SP 800-53 Rev. 5 control family, tailored for SOC 1–2 analysts. Each file maps controls to ISO 27001:2022 clauses and SOX compliance requirements.

## File Structure

```
/Compliance-Mapping/
├── AC.md   # Access Control
├── AT.md   # Awareness and Training
├── AU.md   # Audit and Accountability
├── CA.md   # Security Assessment
├── CM.md   # Configuration Management
├── CP.md   # Contingency Planning
├── IA.md   # Identification & Authentication
├── IR.md   # Incident Response
├── RA.md   # Risk Assessment
├── SC.md   # System & Communication Protection
├── SI.md   # System & Information Integrity
├── SUMMARY.md  # Summary index of all control families
└── README.md  # Index and Overview
```

Each control file includes:

- Summary of control scope
- Mapping to ISO/IEC 27001:2022 Annex A
- Relevance to SOX (esp. Section 302, 404, 802)
- SOC 1–2 Analyst action items
- Examples of detection or audit use

---

## Summary.md

```markdown
# NIST 800-53 Control Family Summary (SOC 1–2 Focus)

| Control ID | File      | Description                        |
|------------|-----------|------------------------------------|
| AC         | [AC.md](AC.md) | Access Control                     |
| AT         | [AT.md](AT.md) | Awareness and Training             |
| AU         | [AU.md](AU.md) | Audit and Accountability           |
| CA         | [CA.md](CA.md) | Security Assessment                |
| CM         | [CM.md](CM.md) | Configuration Management           |
| CP         | [CP.md](CP.md) | Contingency Planning               |
| IA         | [IA.md](IA.md) | Identification and Authentication  |
| IR         | [IR.md](IR.md) | Incident Response                  |
| RA         | [RA.md](RA.md) | Risk Assessment                    |
| SC         | [SC.md](SC.md) | System & Communication Protection  |
| SI         | [SI.md](SI.md) | System & Information Integrity     |
```

---

Let me know if you'd like to add a section for MITRE ATT&CK TTP mappings or links to detection rules per control.
