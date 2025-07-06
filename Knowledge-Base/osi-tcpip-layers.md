# OSI & TCP/IP Layers Relevant to SOC 1 Analyst Operations

## Summary
Outlines OSI and TCP/IP layers most relevant to SOC 1 monitoring and response activities.

## OSI Model – Key Layers

| Layer | Name         | SOC Relevance |
|-------|--------------|---------------|
| 7     | Application  | HTTP/S, DNS, SMB visibility |
| 6     | Presentation | TLS/SSL decryption |
| 5     | Session      | SMB/RDP session hijacking |
| 4     | Transport    | TCP/UDP sessions and port activity |
| 3     | Network      | IP traffic analysis, routing logs |

## TCP/IP Model

| Layer | Name           | SOC Relevance |
|-------|----------------|----------------|
| 4     | Application    | DNS, HTTP, SMB activity |
| 3     | Transport      | TCP/UDP port behavior |
| 2     | Internet       | IP-based reputation, firewall logs |
| 1     | Network Access | MAC/ARP-based activity |

## Use Cases

| Event Type                 | Relevant Layers | Tools |
|---------------------------|------------------|-------|
| RDP brute force           | 3, 4, 7          | Sysmon, Firewall |
| DNS tunneling             | 3, 4, 7          | DNS logs, Zeek |
| Phishing email link       | 7                | Email gateway logs |
| Lateral SMB movement      | 5, 6, 7          | Wazuh, File share logs |
