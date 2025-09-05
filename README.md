# Wazuh SIEM & File Integrity Monitoring Lab  

This project demonstrates the setup and configuration of a **Wazuh SIEM home lab** to monitor logs, detect intrusions, and perform File Integrity Monitoring (FIM). The lab is designed for learning, experimentation, and showcasing cybersecurity skills.  

---

## 🔹 Lab Architecture  

- **Wazuh Manager**: Ubuntu Server (VirtualBox VM)  
- **Wazuh Agent**: Windows host machine  
- **Network Mode**: Bridged (for direct communication between host and VM)  

![Architecture Diagram](architecture.png) *(add your own diagram if possible)*  

---

## 🔹 Features Implemented  

- Deployed **Wazuh Manager** on Ubuntu (VirtualBox) using official installation scripts.  
- Installed and registered **Wazuh Agent** on Windows host for log forwarding.  
- Configured **File Integrity Monitoring (FIM)** to track real-time changes in files/folders.  
- Verified **agent onboarding and alert generation** using the Wazuh Dashboard.  

---

## 🔹 Setup Guide  

### 1. Install Wazuh Manager (Ubuntu VM)  
```bash
curl -sO https://packages.wazuh.com/4.12/wazuh-install.sh
sudo bash ./wazuh-install.sh -a -i
```

### 2. Access Wazuh Dashboard  
- Open browser → `https://<ubuntu-vm-ip>`  
- Login with credentials generated during installation.  

### 3. Install Wazuh Agent (Windows)  
- Download MSI installer from official Wazuh docs.  
- Configure `ossec.conf` with Manager’s IP and agent key.  
- Restart Wazuh Agent service.  

### 4. Configure File Integrity Monitoring (FIM)  
Add this entry in `ossec.conf`:  
```xml
<directories realtime="yes">C:\Users\<YourUser>\Test</directories>
```
Restart the agent service after saving.  

### 5. Test & Verify  
- Create/modify/delete files in the monitored folder.  
- Check the **Integrity Monitoring** tab in Wazuh Dashboard for alerts.  

---

## 🔹 Sample Results  

📌 *Add screenshots like:*  
- Wazuh Dashboard showing connected Windows agent.  
- FIM alerts triggered by file changes.  

---

## 🔹 Skills & Tools Used  
- SIEM (Wazuh)  
- Log Analysis & File Integrity Monitoring  
- Intrusion Detection Concepts  
- Linux (Ubuntu), Windows Administration  
- Virtualization (VirtualBox)  

---

## 🔹 Author  
[Your Name] – Cybersecurity Enthusiast 🚀  
