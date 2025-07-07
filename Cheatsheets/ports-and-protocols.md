| **Port**      | **Protocol** | **Service**                  | **Use Case / Common Alert Context**                                    |
| ------------- | ------------ | ---------------------------- | ---------------------------------------------------------------------- |
| **20/21**     | TCP          | FTP (File Transfer Protocol) | Unencrypted file transfer; check for data exfiltration attempts        |
| **22**        | TCP          | SSH (Secure Shell)           | Remote access; brute force or unauthorized access attempts             |
| **23**        | TCP          | Telnet                       | Unencrypted remote login; should be disabled in secure environments    |
| **25**        | TCP          | SMTP (Mail Transfer)         | Outgoing mail; can indicate spam relay or phishing exfiltration        |
| **53**        | TCP/UDP      | DNS                          | Domain name resolution; DNS tunneling or C2 beaconing possible         |
| **67/68**     | UDP          | DHCP                         | IP address assignment; rogue DHCP servers may be a threat              |
| **80**        | TCP          | HTTP                         | Web traffic; payload delivery, web-based attacks                       |
| **110**       | TCP          | POP3                         | Incoming email (legacy); often flagged in phishing alert traffic       |
| **123**       | UDP          | NTP                          | Time synchronization; large spikes may indicate NTP amplification DDoS |
| **135**       | TCP          | RPC (Windows)                | Lateral movement; DCOM or Mimikatz activity                            |
| **137-139**   | UDP/TCP      | NetBIOS                      | Legacy Windows file sharing; reconnaissance or SMB exploitation        |
| **143**       | TCP          | IMAP                         | Email retrieval; less common but still active in phishing alerts       |
| **161/162**   | UDP          | SNMP                         | Device monitoring; SNMP brute force or enumeration attempts            |
| **389**       | TCP/UDP      | LDAP                         | Directory services; enumeration or AD attacks                          |
| **443**       | TCP          | HTTPS                        | Encrypted web traffic; C2 over HTTPS, phishing pages                   |
| **445**       | TCP          | SMB (Windows)                | File sharing; EternalBlue, lateral movement                            |
| **465/587**   | TCP          | SMTP (Secure/Submission)     | Secure email sending; abused for phishing or spam                      |
| **514**       | UDP          | Syslog                       | Log forwarding; verify centralized logging is active                   |
| **636**       | TCP          | LDAPS                        | Secure LDAP; sensitive for AD infrastructure                           |
| **993/995**   | TCP          | IMAPS / POP3S                | Secure email retrieval; credential theft                               |
| **1433**      | TCP          | MS SQL Server                | Database access; SQL injection or brute force                          |
| **1521**      | TCP          | Oracle DB                    | Database access; uncommon, but monitored in enterprise environments    |
| **3306**      | TCP          | MySQL                        | Database access; watch for exfiltration or injections                  |
| **3389**      | TCP          | RDP                          | Remote Desktop; brute force, lateral movement                          |
| **5432**      | TCP          | PostgreSQL                   | Database activity; unusual access could indicate abuse                 |
| **5900+**     | TCP          | VNC                          | Remote control tools; unauthorized access or shadow IT                 |
| **8000-8080** | TCP          | Proxy/Web App Ports          | Alternate web apps; used in bypasses or dev tools                      |
| **8443**      | TCP          | HTTPS Alt Port               | Encrypted web traffic; common with admin consoles                      |
