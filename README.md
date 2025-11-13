# ☁️ Cloud Log Monitoring & Threat Detection (Wazuh SIEM)

This project demonstrates how to monitor and detect suspicious SSH login activities (such as brute-force and unauthorized access) on a **cloud-hosted Ubuntu VM** using the open-source SIEM tool **Wazuh** (or OSSEC).

---

## 🔍 About the Project
The **Cloud Log Monitoring & Threat Detection Lab** simulates both normal and malicious SSH login attempts on a cloud Ubuntu server.  
By deploying a **Wazuh Manager** and **Wazuh Agent**, the project enables real-time log analysis, correlation, and alert generation using built-in Wazuh rules.

This lab helps in understanding how **Security Information and Event Management (SIEM)** tools enhance visibility, incident detection, and response in a cloud environment.

---

## 🎯 Objective
To detect and alert on suspicious login activities such as brute-force SSH attempts and privilege escalation events using Wazuh’s log monitoring and alerting capabilities.

---

## ⚙️ Tools & Environment

| Component | Description |
|------------|-------------|
| **Cloud Provider** | Oracle Cloud Free Tier / AWS Free Tier |
| **VM 1** | Ubuntu Server 22.04 (Wazuh Agent) |
| **VM 2** | Wazuh Manager / Attacker VM |
| **Logs Monitored** | `/var/log/auth.log` |
| **Ports Used** | 22 (SSH), 5601 (Kibana Dashboard) |
| **SIEM Tool** | Wazuh (with Kibana interface) |

---

## 🧩 Setup Steps

### 1️⃣ Deploy VMs
- Create 2 Ubuntu cloud instances (VM1 and VM2).
- Ensure both can communicate within the same network.

### 2️⃣ Install Wazuh Manager (on VM2)
```bash
curl -sO https://packages.wazuh.com/4.x/wazuh-install.sh
bash wazuh-install.sh -a
