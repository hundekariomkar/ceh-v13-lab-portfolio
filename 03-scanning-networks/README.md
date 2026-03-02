# 03 – Scanning Networks 🌐

## 📌 Lab Overview

This module focuses on network scanning techniques used to identify live hosts, open ports, running services, operating systems, and potential security weaknesses within a target environment.

Scanning was performed in a controlled lab environment consisting of Kali Linux (attacker), Windows 7/10, and Metasploitable 2 as target systems.

---

## 🎯 Objectives

- Perform host discovery within a subnet  
- Identify open TCP and UDP ports  
- Detect running services and versions  
- Perform OS fingerprinting  
- Understand different scan types  
- Analyze IDS/IPS detection considerations  

---

## 🛠 Tools Used

- Nmap  
- Metasploitable 2 (Target VM)  
- Netcat  
- Wireshark (Traffic verification)  

---

## 🔍 Methodology

### 🛰 1. Host Discovery

Used to identify active systems within the network.

nmap -sn (IP Address)

This performed a ping sweep to detect live hosts without scanning ports.

---

### 🚪 2. Port Scanning

#### TCP SYN Scan (Stealth Scan)

nmap -sS (IP Address)

- Fast and less detectable  
- Sends SYN packets without completing handshake  

#### Full TCP Connect Scan

nmap -sT (IP Address)

- Completes full TCP handshake  
- Easier to detect by IDS  

#### Full Port Scan

nmap -p- (IP Address)

- Scans all 65535 ports  

---

### 🔎 3. Service Version Detection

nmap -sV (IP Address)

Identified specific service versions running on open ports, helping determine potential vulnerabilities.

---

### 🖥 4. OS Detection

nmap -O (IP Address)

Used TCP/IP stack fingerprinting to identify target operating system.

---

### 🌊 5. UDP Scanning

nmap -sU (IP Address)

Detected UDP services such as DNS or SNMP which are commonly overlooked but exploitable.

---

## 🔄 Scan Types Understanding

Different scan types impact detection probability:

- Stealth scans reduce detection likelihood  
- Full connect scans are more detectable  
- Aggressive scans increase visibility  

Example Aggressive Scan:

nmap -A (IP Address)

Includes:
- OS detection  
- Version detection  
- Script scanning  
- Traceroute  

---

## 🛡 IDS & IPS Awareness

Intrusion Detection Systems (IDS) and Intrusion Prevention Systems (IPS) monitor abnormal scanning behavior.

Scanning considerations:

- High-speed scans may trigger alerts  
- Full connect scans are easily logged  
- Stealth scans attempt to reduce logging  

Understanding defensive mechanisms is critical for controlled testing and realistic attack simulation.

---

## 📊 Findings

- Identified multiple open ports on Metasploitable 2  
- Detected vulnerable services (e.g., outdated FTP, SMB)  
- Identified target OS fingerprints  
- Observed service banners and exposed versions  

---

## ⚠️ Risk Analysis

Open services may allow:

- Unauthorized access  
- Service exploitation  
- Lateral movement  
- Information disclosure  

Unpatched legacy systems significantly increase attack surface.

---

## 🛡 Mitigation Recommendations

- Close unused ports  
- Implement strict firewall rules  
- Patch outdated services  
- Deploy IDS/IPS monitoring  
- Limit internal network exposure  

---

## 📝 Lab Outcome

Developed practical understanding of structured network scanning, service detection, OS fingerprinting, and defensive monitoring awareness within a controlled penetration testing workflow.
