# Ports and Protocols Cheat Sheet for SOC 1

| Port | Protocol | Service            | SOC 1 Relevance                  |
|------|----------|--------------------|----------------------------------|
| 80   | TCP      | HTTP               | Web activity (non-encrypted)     |
| 443  | TCP      | HTTPS              | Encrypted web traffic            |
| 53   | UDP/TCP  | DNS                | Domain resolution, tunneling     |
| 445  | TCP      | SMB                | File sharing, lateral movement   |
| 3389 | TCP      | RDP                | Remote Desktop login attempts    |
| 25   | TCP      | SMTP               | Outbound email (phishing)        |
