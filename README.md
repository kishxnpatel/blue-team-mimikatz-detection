# 🔐 Blue Team Project: Detecting Mimikatz Credential Dumping with Splunk

## 🎯 Objective
Simulate a real-world credential dumping attack using **Mimikatz**, collect logs with **Sysmon**, and detect the attack using **Splunk custom rules**.

---

## 🛠 Tools Used
- **Windows 10 VM** (VirtualBox)
- **Sysmon** (Microsoft Sysinternals)
- **Splunk Free**
- **Mimikatz** (for controlled lab simulation)

---

## 🔄 Steps Performed (Planned)
1. Set up a Windows 10 lab in VirtualBox.
2. Install & configure Sysmon to capture process execution logs.
3. Forward Sysmon logs to Splunk.
4. Simulate Mimikatz credential dumping (`sekurlsa::logonpasswords`).
5. Write a Splunk detection rule & trigger alerts.

---

## ✅ Expected Outcome
- Splunk should trigger an alert when Mimikatz is executed.
- Logs will show process creation + suspicious LSASS memory access.

---

## 📸 Screenshots (To Be Added)
- Splunk Alert  
- Sysmon Event Logs  
- Mimikatz Execution  

---

## 📄 Lessons Learned
Will be updated after testing.

---

### 📬 Author
**Kishan Patel** – [LinkedIn](https://linkedin.com/in/kishnpatel) | [Portfolio](https://kishxnpatel.com)
