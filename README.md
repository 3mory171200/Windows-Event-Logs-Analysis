# Windows Security Event Logs & SOC Analyst Journey

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
