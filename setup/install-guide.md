# 🛠️ Wazuh Lab Setup Guide

This guide provides step-by-step instructions for setting up a Wazuh environment for threat detection, log analysis, and alerting. It includes installing the Wazuh Manager, registering agents, and integrating with Filebeat for centralized logging.

---

## 1. 🚀 Environment Overview

| Component         | Description                                  |
|------------------|----------------------------------------------|
| Wazuh Manager     | Core SIEM engine for threat detection        |
| Filebeat          | Log shipper for forwarding to Wazuh          |
| Wazuh Agent       | Installed on endpoints (Linux/Windows)       |
| Dashboard         | Web UI for monitoring, alerts & rules        |

---

## 2. 🔧 Wazuh Manager Installation (on Ubuntu)

```bash
curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | sudo apt-key add -
echo "deb https://packages.wazuh.com/4.x/apt/ stable main" | sudo tee /etc/apt/sources.list.d/wazuh.list
sudo apt-get update
sudo apt-get install wazuh-manager

