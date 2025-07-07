# SOC 1 Analyst: Knowledge of Networks

## Why it Matters

As a SOC 1 Analyst, understanding basic network architecture is critical 
for identifying suspicious traffic, analyzing alerts, and tracing 
potential threats back to their origin. SOC 1 focuses on internal controls 
over financial reporting, so any network issues that impact data 
confidentiality, integrity, or availability (CIA) are key compliance 
concerns.

---

## Network Basics a SOC 1 Analyst Should Know

| Concept | Why It Matters for SOC 1 |
|---------|---------------------------|
| IP Addressing (IPv4/IPv6) | Tracks source/destination of events; important for tracing alerts. |
| MAC Address | Identifies the physical device—useful when tracing device-level issues. |
| Ports & Protocols (e.g., HTTP - 80, HTTPS - 443, SMB - 445) | Helps understand which services are being used and how data is transferred. |
| Subnets & VLANs | Key for isolating sensitive data (e.g., financial systems). VLAN misconfigurations can create audit issues. |
| Firewall Rules | Analysts may check if traffic was blocked/allowed during an incident. |
| NAT (Network Address Translation) | Important for understanding internal vs. external IP relationships. |
| DNS & DHCP | Helps track hostname resolution and device identification in logs. |
| Network Topology | Visualizing how devices connect (e.g., flat vs. segmented networks). Segmentation helps meet compliance. |

---

## Network Monitoring and Logging

| Tool/Log Type | Purpose for SOC 1 |
|---------------|-------------------|
| Sysmon Logs (via Wazuh/SIEM) | Detects process creation and network connections. |
| Firewall Logs | Show allowed/blocked traffic; part of audit trails. |
| NetFlow/PCAP | Used for forensic investigation of data flows. |
| SIEM Dashboards | Aggregate network and endpoint logs for real-time monitoring. |

---

## SOC 1-Relevant Use Case Example

**Scenario:** An unauthorized process on a domain controller attempts to 
send data to an external IP over port 443.

**SOC 1 Action:**
- Review Sysmon Event ID 3 (network connection).
- Check firewall logs to verify if the traffic was allowed.
- Correlate the event in SIEM.
- Escalate if the host contains financial records.
- Document evidence and map incident to NIST 800-53 controls (e.g., AC-4, 
SC-7).

---

## Related Controls (NIST 800-53 & SOC 1)

| Control ID | Control Name | Relevance |
|------------|--------------|-----------|
| AC-4 | Information Flow Enforcement | Ensure sensitive data isn’t exfiltrated. |
| SC-7 | Boundary Protection | Network segmentation and firewall policy. |
| AU-12 | Audit Log Generation | Ensures network events are logged and retained. |

