# 08 – Sniffing 📡

## 📌 Lab Overview

This module focuses on network sniffing and Layer-2 attack techniques used to intercept, manipulate, and analyze network traffic. Both passive and active sniffing methods were explored in a controlled lab environment.

The exercises demonstrated how attackers exploit switching mechanisms, ARP protocols, and DHCP infrastructure to perform Man-in-the-Middle (MITM) attacks.

---

## 🎯 Objectives

- Understand passive and active sniffing techniques  
- Perform MAC flooding attacks  
- Conduct DHCP starvation attacks  
- Execute ARP poisoning attacks  
- Detect ARP spoofing activity  
- Perform MAC spoofing  

---

## 🧠 Types of Sniffing

### Passive Sniffing
Occurs in hub-based networks where traffic can be captured without interacting with network devices.

### Active Sniffing
Performed in switched networks using techniques such as ARP poisoning or MAC flooding to intercept traffic.

---

## 🛠 Tools Used

- macof  
- Scapy  
- hping3  
- Yersinia  
- Ettercap  
- Bettercap  
- XARP  
- TMACv6  
- macchanger  
- Kali Linux  

---

## 🔍 Methodology

### 🔄 MAC Flooding using macof

macof -i eth0

Purpose:

- Overflow switch CAM table  
- Force switch into fail-open mode  
- Enable packet sniffing  

---

### 🧪 MAC Flooding using Scapy

Scapy was used to generate custom Ethernet frames to simulate switch table exhaustion.

Impact:

- Broadcast traffic exposure  
- Increased sniffing capability  

---

### ⚡ MAC Flooding using hping3

hping3 --flood --rand-source -S -p 80 192.168.1.10

Purpose:

- Generate high traffic volume  
- Simulate network flooding conditions  

---

### 🌐 DHCP Starvation Attack using Yersinia

DHCP starvation was performed to exhaust IP address pool.

Impact:

- Legitimate clients denied network access  
- Enables rogue DHCP server attacks  

---

### ⚠️ ARP Poisoning using Ettercap

ARP spoofing was performed to intercept communication between hosts.

Purpose:

- Establish MITM position  
- Capture sensitive traffic  

---

### 🧬 ARP Spoofing using Bettercap

Bettercap was used to automate ARP spoofing and traffic interception.

Capabilities:

- Network reconnaissance  
- Traffic manipulation  
- Credential interception  

---

### 🔎 Detecting ARP Poisoning using XARP

XARP was used to detect abnormal ARP activity.

Detection indicators:

- Duplicate ARP replies  
- Suspicious MAC-IP mappings  
- MITM attack alerts  

---

### 🧾 MAC Spoofing using TMACv6

TMACv6 was used to change network interface MAC address on Windows systems.

Purpose:

- Identity masking  
- Network access bypass  

---

### 🐧 MAC Spoofing using macchanger

macchanger -r eth0

Used to randomize MAC address on Linux systems.

---

## 📊 Findings

- Successfully simulated MAC flooding conditions  
- Demonstrated DHCP infrastructure exhaustion  
- Intercepted network traffic using ARP poisoning  
- Detected spoofing attacks via XARP  
- Altered device identity using MAC spoofing  

---

## ⚠️ Risk Analysis

Layer-2 attacks may lead to:

- Credential interception  
- Network session hijacking  
- Denial of service conditions  
- Unauthorized network access  
- Traffic manipulation  

Switch misconfiguration significantly increases risk exposure.

---

## 🛡 Mitigation Recommendations

- Enable port security on switches  
- Implement DHCP snooping  
- Use Dynamic ARP Inspection (DAI)  
- Deploy network intrusion detection systems  
- Monitor abnormal MAC address changes  
- Segment critical network infrastructure  

---

## 📝 Lab Outcome

Developed practical understanding of network sniffing techniques, Layer-2 attack vectors, and defensive detection mechanisms within structured penetration testing scenarios.
