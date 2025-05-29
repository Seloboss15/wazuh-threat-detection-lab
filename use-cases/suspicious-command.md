🛡️ Suspicious Command Detection (Simulated Attack)

 🔍 Overview

In this exercise, we simulate a suspicious command execution using `netcat` (`nc`), a common tool leveraged by attackers to establish reverse shells or transfer files. We'll use Wazuh to detect and generate alerts when such commands are executed on a monitored system.


 ⚙️ Environment Setup

Operating System: Ubuntu (Virtual Machine)
Monitoring Tool: Wazuh 4.12.0
Log Source: auditd (Linux Audit Daemon)

Ensure your Wazuh manager and dashboard are properly installed and accessible.


## 🧪 Step 1: Install and Configure `auditd`

Auditd logs system-level events, including command executions.

```bash
sudo apt update
sudo apt install auditd -y
sudo systemctl enable auditd
sudo systemctl start auditd

