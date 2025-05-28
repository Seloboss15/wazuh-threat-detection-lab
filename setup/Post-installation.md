# Wazuh Manager Post-Installation Guide

This guide walks you through what to do immediately after installing the Wazuh Manager.

---

## 1. Start the Wazuh Manager service

```bash
sudo systemctl start wazuh-manager
```

## 2. Enable Wazuh Manager to start at boot

```bash
sudo systemctl enable wazuh-manager
```
## 3. Check the Status of Wazuh Manager

```bash
sudo systemctl status wazuh-manager
