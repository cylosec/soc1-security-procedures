# DNS Tunneling – SOC Analyst Knowledge Base

## Overview

**DNS Tunneling** is a technique used by attackers to encapsulate data within DNS queries and responses. It enables:
- Covert data exfiltration
- Command-and-control (C2) communication
- Firewall/proxy evasion

Attackers exploit the fact that DNS traffic (UDP/53 or TCP/53) is typically unrestricted and unmonitored in many networks.

---

## How DNS Tunneling Works

1. **Compromised host** encodes data into DNS requests to attacker-controlled domains.
2. The **subdomain** (e.g., `payload.attacker.com`) contains encoded data (Base64, Hex, etc.).
3. An **attacker's DNS server** decodes the request and optionally sends back encoded instructions.
4. This results in **bi-directional communication** over DNS.

---

## MITRE ATT&CK References

- **T1071.004** – Application Layer Protocol: DNS  
- **T1568** – Dynamic Resolution  
- **T1043** – Commonly Used Port

---

## Detection Indicators

### In EDR:
- Execution of unusual DNS tools by user-level processes:
  - `nslookup`, `dig`, `certutil`, `powershell`, `python`
- Suspicious parent-child process chains:
  - `cmd.exe` → `nslookup.exe`
  - `powershell.exe` spawning DNS lookups
- Long or encoded subdomains in queries
- DNS queries from non-standard binaries or directories

### In SIEM:
- Large volume of DNS queries to:
  - A single domain or rare destination
  - Domains with dynamic/randomized subdomains
- Long query strings (>60 characters)
- High number of **NXDOMAIN** responses
- Queries using uncommon TLDs or dynamic DNS providers
- DNS traffic outside normal working hours

---

## Sample DNS Query Patterns

| Query Example | Suspicious Indicator |
|---------------|----------------------|
| `a1b2c3d4.attacker.com` | Encoded subdomain |
| `test.data1234567890.command.attacker.site` | C2 instructions embedded in query |
| `x.abc.com` every 2 seconds | High-frequency DNS queries |

---

## Sample SIEM Rule (Pseudocode)

```plaintext
event.module: dns
AND dns.query.length > 60
AND dns.query LIKE "%.%"
AND dns.query_count > 100 in 1 hour
AND response_code == NXDOMAIN
