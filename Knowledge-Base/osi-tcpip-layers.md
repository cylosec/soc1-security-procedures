# OSI & TCP/IP Layers Relevant to SOC 1 Analyst Operations

## Summary
Outlines OSI and TCP/IP layers most relevant to SOC 1 monitoring and response activities.

## OSI Model – Key Layers

| **Layer** | **Name**     | **SOC Relevance**                                                   |
| --------- | ------------ | ------------------------------------------------------------------- |
| 7         | Application  | User behavior, phishing, HTTP/S traffic, DNS tunneling, SMB shares. |
| 6         | Presentation | TLS/SSL decryption visibility, encrypted payload analysis.          |
| 5         | Session      | Session hijacking, SMB/NFS session abuse, RDP session monitoring.   |
| 4         | Transport    | TCP/UDP session behavior, port scans, DoS detection.                |
| 3         | Network      | IP addresses, routing paths, firewall and IDS correlation.          |

## TCP/IP Model

| **Layer** | **Name**       | **SOC Relevance**                                            |
| --------- | -------------- | ------------------------------------------------------------ |
| 4         | Application    | HTTP/S, FTP, SMTP, DNS — high visibility in logs and alerts. |
| 3         | Transport      | TCP/UDP flow, port-specific attacks (e.g., RDP brute force). |
| 2         | Internet       | IP-based reputation checks, geo-IP analysis.                 |
| 1         | Network Access | MAC spoofing, ARP poisoning (less common at SOC 1 level).    |


## Use Cases Examples

| **Event Type**              | **Relevant Layers** | **Tools/Logs**                        |
| --------------------------- | ------------------- | ------------------------------------- |
| Phishing link in email      | Layer 7             | Email gateway logs, browser telemetry |
| RDP brute-force attempt     | Layers 3, 4, 7      | Firewall logs, Sysmon, Windows Events |
| DNS tunneling               | Layers 3, 4, 7      | DNS logs, Zeek, Suricata alerts       |
| Data exfiltration via HTTPS | Layers 4, 7         | PCAP, NetFlow, proxy logs             |
| Lateral movement via SMB    | Layers 5, 6, 7      | Sysmon, network shares, audit policy  |



