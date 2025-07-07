# SOC 1 Analyst: Common Bash Commands

This reference guide provides commonly used Bash commands in a SOC 1 Analyst workflow. These commands assist with log analysis, user auditing, network inspection, and system triage—especially in environments monitored by Wazuh or similar SIEM platforms.

---

## Log Inspection

```bash
# View real-time system logs
tail -f /var/log/syslog
tail -f /var/log/auth.log

# Wazuh logs
less /var/ossec/logs/ossec.log

# Search for specific terms
grep "failed" /var/log/auth.log
grep "unauthorized" /var/ossec/logs/ossec.log
```

---

## File Integrity Monitoring (FIM)

```bash
# Get file hashes for integrity verification
sha256sum /etc/passwd
md5sum /etc/shadow

# List file metadata recursively
find /etc -type f -exec stat {} \;
```

---

## User and Access Verification

```bash
# Check logged in users
who
w
last

# View all user accounts
cat /etc/passwd

# Find accounts with root privileges
awk -F: '$3 == 0 { print $1 }' /etc/passwd
```

---

## Network Inspection

```bash
# Display listening ports and bound services
ss -tuln
netstat -tulnp

# Show established connections
netstat -an | grep ESTABLISHED

# Trace path to remote IP
traceroute <IP_ADDRESS>

# DNS resolution
nslookup example.com
dig example.com
```

---

## Process and System Monitoring

```bash
# Show running processes
ps aux

# Process tree
pstree

# Live resource monitor
top
htop
```

---

## Basic Triage and Response

```bash
# Kill suspicious process by PID
kill -9 <PID>

# Lock user account
usermod -L <username>

# Check cron jobs
crontab -l
ls -la /etc/cron*
```

---

## Wazuh-Specific Commands

```bash
# Restart Wazuh manager (on server)
systemctl restart wazuh-manager

# Restart Wazuh agent (on endpoint)
systemctl restart wazuh-agent

# List all connected agents
/var/ossec/bin/agent-control -l
```

---

## Pro Tip: Log Your Terminal Session

```bash
# Record investigation session
script investigation_session.log

# Log output of commands
your_command | tee -a log_output.txt
```

---

Note: These commands are typically used for triage, validation, and support within a SOC Level 1 role. System-level changes (e.g., disabling users or restarting services) should follow change management and incident response procedures.

