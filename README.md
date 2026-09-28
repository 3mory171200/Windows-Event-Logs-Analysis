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




Windows Security Event Logs & SOC Analyst Journey
Welcome to my security investigation repository! Here I document my hands-on learning journey in Security Operations Center (SOC) operations, threat hunting, and Windows event log analysis.

🔍 Part 1: System Monitoring & Sysmon Event Analysis
Overview of Sysmon (System Monitor): An advanced background monitoring tool that provides granular insights into process activity, network connections, and system alterations.

Key Sysmon Event IDs Mastered:

Event ID 1 (Process Create): Captures process execution details along with full command-line arguments.

Event ID 3 (Network Connection): Tracks outbound and inbound network traffic associated with specific processes.

Event ID 5 (Process Terminated): Logs when a process completes or stops.

Event ID 11 (File Creation): Essential for tracking dropped malware files and persistence mechanisms.

Event ID 13 (Registry Event): Monitors modifications made to Windows registry keys used for persistence.

Event ID 22 (DNS Query): Records DNS lookups initiated by processes on the system.

Log Correlation Methodology: Disparate logs are linked together using unique identifiers such as Logon ID and Process ID to reconstruct the full attack chain from initial access to execution.   
<img width="1908" height="1065" alt="image" src="https://github.com/user-attachments/assets/b0f1f029-0236-4e0d-8fec-aa8df5191a9b" />   





Part 2: PowerShell Logging & History Analysis
The Monitoring Challenge: Traditional process creation logs (like Sysmon Event ID 1) only indicate that powershell.exe was launched, failing to capture granular internal commands since an attacker can execute hundreds of commands within a single active session.

The Forensic Artifact (ConsoleHost_history.txt): PowerShell automatically maintains a plain text history file that records every command entered, updating in real-time upon pressing Enter:

%appdata%\Microsoft\Windows\PowerShell\PSReadLine
<img width="1772" height="794" alt="image" src="https://github.com/user-attachments/assets/be17ccd0-4792-479b-aa8e-7b133ba59300" />


