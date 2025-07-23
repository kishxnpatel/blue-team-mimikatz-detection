# 🔐 Blue Team Project: Detecting Mimikatz with Splunk + Sysmon

## 🎯 What This Project Is About
This lab is all about **catching a credential dumping attack (Mimikatz)** using **Sysmon logs** and **Splunk**.  
I wanted to simulate how a Blue Team would detect suspicious activity in a real environment.

---

## 🛠 What We Used
- **Windows 10 VM (VirtualBox)**
- **Sysmon** (to collect detailed process and command-line logs)
- **Splunk Free** (to ingest logs and create detection rules)
- **Mimikatz** (attacker simulation)

---

## ✅ What We Did (Step by Step)
1. **Set up Windows 10 VM in VirtualBox**  
   - Installed a clean Windows 10 and took a snapshot for safety.  
   <!-- Screenshot: VirtualBox Windows running -->

2. **Installed Sysmon and Applied a Good Config**  
   - Used SwiftOnSecurity’s community config to capture process creation, network connections, etc.  
   - Verified logs in **Event Viewer → Sysmon Operational**.  
   <!-- Screenshot: Sysmon logs in Event Viewer -->

3. **Installed Splunk and Ingested Sysmon Logs**  
   - Added `Microsoft-Windows-Sysmon/Operational` logs to Splunk.  
   - Confirmed events were visible in Splunk search.  
   <!-- Screenshot: Splunk showing Sysmon events -->

4. **Simulated the Attack with Mimikatz**  
   - Ran `privilege::debug` and `sekurlsa::logonpasswords` to mimic credential dumping.  
   <!-- Screenshot: Mimikatz running in CMD -->

5. **Detected the Attack in Splunk**  
   - Searched for `*mimikatz*` in logs and confirmed multiple process creation events.  
   - Created a Splunk alert called **“Mimikatz Execution Detected.”**  
   <!-- Screenshot: Splunk search results -->
   <!-- Screenshot: Splunk alert configuration -->

---

## 🔍 What We Learned
- **Sysmon is great** for collecting rich process execution logs that Windows Event Logs normally miss.
- **Mimikatz activity is noisy** — it can easily be caught if you monitor process names and suspicious command lines.
- **Splunk makes detection easier** by allowing custom alerts, even in small lab setups.

---

## 🚀 What’s Next
- Add more detections for **LSASS memory access** or **network beacons**.  
- Build a small dashboard in Splunk for live monitoring.

---

## 📬 Author
**Kishan Patel**  
- [LinkedIn](https://linkedin.com/in/kishnpatel)  
- [Portfolio](https://kishxnpatel.com)
