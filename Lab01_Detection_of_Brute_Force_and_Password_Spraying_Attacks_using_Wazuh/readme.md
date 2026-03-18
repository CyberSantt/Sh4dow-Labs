# 🔐 Lab01_Detection_of_Brute_Force_and_Password_Spraying_Attacks_using_Wazuh

## 🧠 Skills Demonstrated
- Log analysis
- Threat detection
- SIEM rule creation
- Attack simulation
- Event correlation

---

## 📌 Overview
This lab demonstrates how Brute Force attacks & Password Spraying attacks can be simulated and detected using Wazuh

The objective is to analyze authentication behavior, generate logs, and detect anomalies through custom SIEM rules.

---

## 🎯 Objectives
- Simulate [attack: brute force / password spraying / etc.]
- Collect and analyze logs from [Windows / Linux / etc.]
- Develop custom detection rules
- Validate alerts in the SIEM
- Understand attacker behavior and detection patterns

---

## 🛠️ Technologies Used
- Wazuh (SIEM)
- Kali Linux
- Hydra (Attack simulation)
- Windows Server (Target machine)

---

## 🧪 Lab Setup
- Attacker machine: Kali Linux
- Target machine: Windows Server 
- Network: Bridge
- Log source: Windows Event Logs (Event ID 4624 / 4625)

---

## ⚔️ Attack Simulation

###  🔹 Brute Force
Description of the attack:
 - Single user targeted
 - Multiple password attempts

Example command: hydra -l user -P passwords.txt smb://target_ip

### 🔹 Password Spraying
Description of the attack:
 - Multiple users targeted
 - Same password used across accounts

Example command: hydra -L users.txt -P passwords.txt smb://target_ip

---

## 📊 Log Collection
Logs were collected from Windows Security Events:
    4625 → Failed logon
    4624 → Successful logon
These events were used to identify authentication anomalies.

---

## 🚨 Detection Rules
- Rule 100500 Detects brute force attacks.
- Rule 100504 Detects password spraying behavior across multiple users.
- Rule 100510 Windows Event 4625.

---

## 📈 SIEM Visualization
The following dashboards were created:
 - Top attacking IPs
 - Most targeted users
 - Login failures over time
 - Successful logins
 - Failed vs successful login ratio

---

## 🔍 Key Findings
- Multiple failed login attempts detected from a single IP
- Password spraying behavior identified across multiple users
- A successful authentication was achieved after multiple failed attempts
- Detection rules successfully triggered alerts

---

## ⚠️ Notes
Sensitive data such as IP addresses and passwords have been redacted.

---

## 📁 Repository Content
/Screenshots → dashboards and logs
/Scripts → attack outputs
/Report → PDF documentation

---

## 💬 Feedback
Feedback, suggestions, and constructive criticism are highly appreciated to keep improving this project.
