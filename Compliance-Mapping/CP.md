# NIST 800-53 Control Family: CP – Contingency Planning

## Summary
Ensures systems can recover from outages, cyberattacks, or other disasters.

## ISO/IEC 27001 Mapping
- **A.5.29** – Information security during disruption
- **A.5.30** – ICT continuity planning

## SOX Relevance
- Not directly required, but strongly related to risk mitigation

## SOC 1–2 Analyst Action Items
- Monitor for backup failures
- Alert on ransomware behavior (e.g., rapid encryption events)
- Review BCP and DR test results when available

## Detection/Audit Examples
- SIEM alert for unusual spike in file writes
- Missed backup task from backup software logs
