<img width="1909" height="1077" alt="image" src="https://github.com/user-attachments/assets/d6eb242a-d9ad-4b0d-8cce-716280729257" /># Windows Security Event Logs & SOC Analyst Journey

Welcome to my security investigation repository! Here I document my hands-on learning journey in **Security Operations Center (SOC)** operations, threat hunting, and Windows event log analysis.

## 🛡️ Key Concepts & Event IDs Mastered
As an aspiring SOC analyst, I am focusing on analyzing core Windows security events using `Event Viewer`:

* **Event ID 4625 (Logon Failure):** Investigating failed authentication attempts to detect potential Brute Force or unauthorized access vectors.
* **Event ID 4688 (Process Creation):** Monitoring command-line execution (`CommandLine`) and analyzing process relationships (`ParentProcessName`) to identify suspicious activities or malicious execution paths.
* **Event ID 4624 (Logon Success):** Tracking successful logins and differentiating between logon types.

---
## 🔍 Sample Investigation: Detecting Brute Force (Event 4625)
* **Tool Used:** Windows Event Viewer (`eventvwr.msc`)
* **Filtering Technique:** Navigated to `Security` logs -> Applied filter for `Event ID: 4625`.
* **Findings:** Identified audit failures indicating unauthorized login attempts and correlated event properties to evaluate potential threats.

---
*Created by **Amer Elbaba***
<img width="1909" height="1077" alt="8fc8397f-3419-48a7-816a-35c742cb644d" src="https://github.com/user-attachments/assets/d2867f14-3f23-4e14-8853-9ddb4751be3d" />
