# Wazuh + Splunk Integration (Capability Notes)

## Purpose
To simulate how a Security Operations Center (SOC) can forward and visualize Wazuh alerts inside Splunk Enterprise using JSON data, real-time log shipping, and automation workflows.

## Background
Splunk is used at many enterprises. Although I am currently using Splunk Enterprise Free version, I am still able to utilize capabilities for integration. I’ve configured my Wazuh lab in a way that mimics how alerts would be forwarded and parsed by Splunk.

---

## Integration Design (Planned/Capable)

### 1. Source: Wazuh JSON Alerts
- File: `/var/ossec/logs/alerts/alerts.json`
- Format: JSON
- Includes MITRE mappings, rule level, process/user data

### 2. Log Forwarding Options
- **Filebeat → Splunk HEC**  
  Lightweight agent that ships Wazuh alerts to Splunk using HTTP Event Collector.
  
- **Logstash → Splunk TCP**  
  Allows parsing/enrichment of JSON before forwarding to Splunk.

---

## Splunk Configuration (Expected)

### Data Indexing
- Index: `wazuh_alerts`
- Source Type: `json`
- Fields: `agent.name`, `rule.level`, `mitre.id`, `data.srcip`, `full_log`

### Search Example
```spl
index=wazuh_alerts rule.level>=10 | stats count by agent.name, rule.description
