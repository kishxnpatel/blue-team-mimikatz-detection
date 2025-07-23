# 🔐 Blue Team Project: Detecting Mimikatz with Splunk + Sysmon

## 🎯 What This Project Is About
This lab simulates how a **Blue Team can detect credential dumping attacks** using **Sysmon** and **Splunk**.  
I ran a real **Mimikatz attack** in a controlled Windows 10 VM and created a detection alert in Splunk.  

---

## 🛠 Tools & Setup
- **Windows 10 VM (VirtualBox)**
- **Sysmon** (with SwiftOnSecurity’s config)
- **Splunk Free**
- **Mimikatz (for simulation)**

---

## ✅ What We Did

### 1. Set up Windows 10 VM
Created a fresh Windows 10 VM on VirtualBox.  
![Windows VM](screenshots/Windows.png)  
(Optional initial setup screenshot)  
![Windows Setup](screenshots/Winsetup.png)

---

### 2. Installed Sysmon and Verified Logs
- Installed Sysmon with community config to log process creation and command-line activity.  
- Confirmed logs in Event Viewer under **Sysmon → Operational**.  
![Sysmon Installation](screenshots/Sysmon.png)  
![Sysmon Event Viewer](screenshots/sysmonevent.png)

---

### 3. Installed Splunk and Ingested Sysmon Logs
- Installed Splunk and added the Sysmon Operational logs.  
- Confirmed logs are streaming into Splunk.  
![Splunk Sysmon Events](screenshots/events.png)

---

### 4. Simulated an Attack with Mimikatz
- Ran the following commands inside the Windows VM:
