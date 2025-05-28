# # Wazuh Threat Detection Lab

This project showcases a hands-on lab environment built with Wazuh to demonstrate real-world threat detection, endpoint monitoring, and alert analysis. It is designed as part of my portfolio as a Security Analyst and SOC professional.

---

## 🏗️ Lab Architecture

- **SIEM Tool**: Wazuh (latest version)
- **Log Sources**: Windows Event Logs, Linux Syslog, Sysmon
- **Agents**: Windows 10, Ubuntu Server
- **Monitoring Capabilities**: File integrity, rootkit detection, log analysis, active response

---

## 🔧 Setup Guide

The full setup and installation steps for Wazuh server and agents are located in [setup/install-guide.md](setup/install-guide.md).

Includes:
- Wazuh Manager installation
- Agent installation & registration
- Filebeat integration for log forwarding
- Enabling custom modules (e.g., rootcheck, syscheck)

---

## 🧠 Detection Use Cases

Explore detection scenarios documented in the [use-cases](use-cases) folder:

| Use Case               | Summary                                  |
|------------------------|------------------------------------------|
| Brute Force Detection  | SSH login failures triggering alerts     |
| Malware Execution      | Simulated malware behavior caught by rules |
| Suspicious Commands    | PowerShell or bash commands detection    |

---

## 🔍 Custom Rules

View detection rules and customizations under [`detection-rules`](detection-rules/).  
Includes custom `.xml` rules and detailed descriptions of what each rule does and why it matters.

---

## 🚨 Alerts

The [`alerts`](alerts/) folder contains:
- Sample alerts in JSON format
- Manual triage notes and analysis for selected alerts

---

## 🖼️ Screenshots & Architecture

Find dashboard screenshots and diagrams in [`setup/screenshots`](setup/screenshots).

---

## 🙋 About Me

Hi, I'm Selome Asokere, a Security Analyst passionate about cybersecurity operations, SIEM tools, and building resilient detection systems. This lab is one of many in progress to showcase the tools I work with — including Splunk, Microsoft Sentinel, and Wazuh.

Stay tuned for more updates.

---

> ⭐️ If this project resonates with your team or company, feel free to reach out or connect!