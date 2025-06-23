# 28811-Wipro_Capstone
Brute Force via Kali Linux on Windows Server 2022
Here’s a clean and professional GitHub-style documentation you can use for your incident response project. You can copy this into a `README.md` file in your repository:

```markdown
# 🛡️ Windows Server Brute-Force Attack Simulation – Incident Response Report

## 📌 Overview
This repository documents a simulated brute-force attack using Hydra on a Windows Server. It includes the attack methodology, root cause analysis, mitigation steps, and post-incident actions.

---

## ⚔️ Attack Summary

- **Tool Used:** Hydra
- **Target Protocol:** RDP (Remote Desktop Protocol)
- **Attack Type:** Dictionary-based brute-force
- **Command Example:**
  ```bash
  hydra -t 1 -V -f -l administrator -P rockyou.txt rdp://<target_ip>
  ```

---

## 🧠 Root Cause

The system lacked proper brute-force protection mechanisms:
- No account lockout policy
- Weak password enforcement
- Inbound RDP access was unrestricted

---

## 🔥 Firewall Rule (PowerShell)

To simulate the attack, an inbound rule was created to allow RDP traffic:
```powershell
New-NetFirewallRule -DisplayName "Allow RDP" -Direction Inbound -Protocol TCP -LocalPort 3389 -Action Allow
```

---

## 🛠️ Mitigation Steps

- Enforced account lockout after 5 failed attempts
- Enabled MFA for remote access
- Restricted RDP access to internal IPs only
- Hardened password policies

---

## 🧯 Incident Response Playbook

### 1. Isolation
- Disconnected affected system from the network
- Disabled compromised accounts
- Blocked attacker IPs

### 2. Recovery
- Restored system from clean backup
- Patched vulnerabilities
- Reset all credentials

### 3. Post-Incident
- Conducted lessons-learned session
- Updated response playbook
- Shared IOCs with internal teams

---

## 📊 Risk Assessment

| Factor               | Rating | Notes                                      |
|----------------------|--------|--------------------------------------------|
| Likelihood           | High   | Common attack vector                       |
| Impact               | High   | Full system access possible                |
| Detection Capability | Low    | No alerts triggered during attack          |
| Mitigation Effort    | Low    | Mostly policy and config-based fixes       |

---

## 📁 Folder Structure

```
/incident-response/
├── README.md
├── logs/
│   └── hydra-output.txt
├── scripts/
│   └── firewall-rule.ps1
├── reports/
│   └── root-cause-analysis.md
```

---

## 📬 Contact

For questions or contributions, open an issue or submit a pull request.

```
Here’s a fresh batch of Root Cause Analysis (RCA) content you can drop into your GitHub `README.md`, complete with emoji-style icons for visual clarity and structure:

---

## 🧩 Root Cause Analysis (RCA) Components

### 🔍 Problem Statement
Clearly define the issue observed during the security assessment or incident.

> *Example:* "Unauthorized access was detected on the Windows Server via RDP."

### 🧠 Root Cause
Identify the underlying reason the issue occurred.

> *Example:* "Lack of account lockout policy allowed brute-force login attempts."

### 🧪 Contributing Factors
List any secondary issues that made the problem worse.

- 🔓 Weak password policy  
- 🌐 Unrestricted RDP access  
- 🚫 No intrusion detection or alerting  

### 🧰 Tools & Techniques Used
Mention tools used for analysis and testing.

- 🛠️ Hydra for brute-force simulation  
- 🧱 PowerShell for firewall rule creation  
- 📜 Event Viewer for log analysis  

### 📈 Impact Assessment
Describe the potential or actual damage caused.

> *Example:* "Successful brute-force attack could lead to full system compromise."

### 🛡️ Mitigation & Prevention
Summarize the fixes and how to prevent recurrence.

- ✅ Enforced account lockout  
- 🔐 Enabled MFA  
- 🔥 Restricted RDP to internal IPs  
- 📊 Enabled login failure alerts  

---
Contact - AnujDev67
or DM 


