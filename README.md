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

Want me to help you generate the folder structure or add visuals like a timeline or attack flow diagram? I can also help you turn this into a PDF or HTML page.

