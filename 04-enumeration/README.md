# 04 – Enumeration 🧭

## 📌 Lab Overview

Enumeration is the process of actively extracting detailed information from target systems after identifying open ports during the scanning phase.

This module focused on gathering usernames, domain information, network services, and exposed file systems through structured service-level interaction in a controlled lab environment.

---

## 🎯 Objectives

- Perform NetBIOS enumeration  
- Extract system information using SNMP  
- Enumerate Active Directory via LDAP  
- Identify exposed NFS shares  
- Perform DNS service enumeration  
- Extract SMTP user information  

---

## 🛠 Tools Used

- Nmap  
- nbtstat  
- SnmpWalk  
- Active Directory Explorer  
- rpcinfo  
- showmount  
- SuperEnum  
- DNS utilities (nslookup, dig)  
- SMTP utilities (Netcat / Telnet)  
- Kali Linux  
- Windows 7 / Windows Server  
- Metasploitable 2  

---

## 🔍 Methodology

### 🖥 NetBIOS Enumeration

Used to retrieve NetBIOS name tables and shared resource information.

**nbtstat -A (IP Address)**

**nbtstat -c**

Extracted:

- NetBIOS computer name  
- Workgroup/domain details  
- Cached NetBIOS entries

---

### 📡 SNMP Enumeration

Used SNMP to extract system and network configuration data.

**snmpwalk -v1 -c public (IP Address)**

Enumerated:

- System description  
- Network interfaces  
- Running services  
- Routing tables  

---

### 🏢 LDAP Enumeration

Used Active Directory Explorer to enumerate domain directory information.

Extracted:

- User accounts  
- Group memberships  
- Organizational units  
- Domain hierarchy  

LDAP enumeration helps understand privilege relationships within domain environments.

---

### 📂 NFS Enumeration

Identified exposed file shares in Linux environments.

**rpcinfo -p (IP Address)**

**showmount -e (IP Address)**

SuperEnum was used to automate multi-service enumeration.

Discovered:

- Exported directories  
- RPC services  
- Access permissions  

---

### 🌐 DNS Enumeration

Used DNS queries to gather domain-related information.

**nslookup example.com**

**dig example.com**

Enumerated:

- Name servers  
- Mail exchange records  
- Domain IP mappings  
- Subdomain hints  

---

### 📧 SMTP Enumeration

Used SMTP interaction to identify valid users.

Example:

**nc (IP Address)**

or

**telnet (IP Address)**

Possible enumeration commands:

- VRFY  
- EXPN  

Extracted:

- Valid usernames  
- Mail server banner information  

---

## 📊 Findings

- Identified NetBIOS host details  
- Retrieved system data via SNMP  
- Enumerated Active Directory structure  
- Discovered exposed NFS shares  
- Gathered DNS configuration data  
- Identified SMTP user validation responses  

---

## ⚠️ Risk Analysis

Enumeration exposed critical internal details that could lead to:

- Credential attacks  
- Privilege escalation  
- Sensitive data exposure  
- Domain compromise  
- Targeted phishing campaigns  

Unrestricted service visibility significantly increases attack surface.

---

## 🛡 Mitigation Recommendations

- Disable unnecessary NetBIOS services  
- Harden SNMP configuration (use SNMPv3)  
- Restrict LDAP access  
- Secure NFS exports  
- Implement DNS security controls  
- Disable SMTP user enumeration  
- Monitor abnormal enumeration activity  

---

## 📝 Lab Outcome

Developed structured service-level intelligence gathering skills across multiple protocols including NetBIOS, SNMP, LDAP, NFS, DNS, and SMTP, understanding how enumeration bridges scanning and exploitation phases in penetration testing.
