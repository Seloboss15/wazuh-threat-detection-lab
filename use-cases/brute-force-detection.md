# 🚨 Windows Brute Force Detection with Wazuh

## 🔍 Use Case Overview
Detect brute force login attempts on a Windows host using Wazuh's log analysis and correlation capabilities.


## 🛠️ Objective
Identify multiple failed logon attempts within a short time period that may indicate brute force activity.


## 🗂️ Log Source
- Windows Event Logs
- Event ID: **4625** (An account failed to log on)


## 📏 Detection Logic
Correlate multiple `Event ID 4625` entries within a short time frame (e.g., 5 minutes) from the same source IP or user.


## 🧪 Sample Log Snippet

```json
{
  "win.system.eventID": "4625",
  "win.system.providerName": "Microsoft-Windows-Security-Auditing",
  "win.eventdata.TargetUserName": "Administrator",
  "win.eventdata.IpAddress": "192.168.1.101"
}

