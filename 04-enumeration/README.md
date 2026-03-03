# 04 – Enumeration 🧭

## 📌 Lab Overview

Enumeration involves actively extracting detailed information from target systems and services after identifying open ports during the scanning phase.

This module focused on extracting usernames, shares, directory services data, and exposed network file systems using structured enumeration techniques within an isolated lab environment.

---

## 🎯 Objectives

- Perform NetBIOS enumeration  
- Enumerate services using Windows command-line utilities  
- Extract information via SNMP  
- Enumerate LDAP directory services  
- Identify exposed NFS shares  

---

## 🛠 Tools Used

- Nmap  
- NetBIOS utilities  
- Windows Command Line tools  
- SnmpWalk  
- Active Directory Explorer  
- RPCScan  
- SuperEnum  
- Kali Linux  
- Windows 7 / Windows Server  
- Metasploitable 2  

---

## 🔍 Methodology

---

### 💻 NetBIOS Enumeration using Windows Command Line Utilities

Used built-in Windows tools to extract NetBIOS-related information.

#### 1. Retrieve Remote NetBIOS Name Table

** nbtstat -A (IP Address) **

This command retrieved:

- NetBIOS computer name  
- Workgroup/domain name  
- Registered services  
- MAC address  

It provides insight into host identity and network role.

---

#### 2. Display NetBIOS Name Cache

** nbtstat -c (IP Address) **

This displayed:

- Locally cached NetBIOS names  
- Resolved remote host mappings  

This helps identify previously contacted systems and potential internal network relationships.

---

### 📡 SNMP Enumeration using SnmpWalk

Simple Network Management Protocol (SNMP) was enumerated to extract system and network-level information from the target host.

SNMP is commonly misconfigured with default community strings such as `public`, which allows attackers to gather sensitive information without authentication.

#### Command Used:

** snmpwalk -v1 -c public (IP Address) **

Where:

- `-v1` → Specifies SNMP version 1  
- `-c public` → Community string (default value)  
- `IP Address` → Target host IP  

---

### 🔍 Information Extracted

Using SNMP enumeration, the following data was retrieved:

- System description  
- Hostname  
- Network interfaces  
- Routing information  
- Running services  
- Installed software (in some cases)  

SNMP can expose significant internal configuration details if not properly secured.

---

### ⚠️ Risk Analysis

Misconfigured SNMP services may allow attackers to:

- Map internal network infrastructure  
- Identify running services and versions  
- Discover system details for targeted exploitation  
- Gather reconnaissance data without authentication  

Default community strings such as `Public` and `Private` pose serious security risks.

---

### 🛡 Mitigation Recommendations

- Disable SNMP if not required  
- Change default community strings  
- Restrict SNMP access using firewall rules  
- Use SNMPv3 with authentication and encryption  
- Monitor SNMP access logs

---

### 🏢 LDAP Enumeration using Active Directory Explorer

Lightweight Directory Access Protocol (LDAP) enumeration was performed to extract structured directory information from the Active Directory environment.

Active Directory Explorer was used to connect to the domain controller and analyze directory objects.

---

### 🔍 Information Retrieved

Using LDAP enumeration, the following data was gathered:

- Domain name  
- Organizational Units (OUs)  
- User accounts  
- Group memberships  
- Service accounts  
- Computer objects  
- Domain structure hierarchy  

LDAP provides deep visibility into domain-based environments.

---

### 🎯 Purpose of LDAP Enumeration

LDAP enumeration helps attackers and security professionals:

- Identify valid user accounts  
- Map domain trust relationships  
- Discover privilege levels  
- Locate service accounts  
- Understand domain hierarchy  

This information is critical for privilege escalation and lateral movement scenarios.

---

### ⚠️ Risk Analysis

Unrestricted LDAP access may lead to:

- Exposure of sensitive user information  
- Credential-based attacks  
- Privilege escalation  
- Domain compromise  

Improperly secured directory services significantly increase attack impact.

---

### 🛡 Mitigation Recommendations

- Restrict anonymous LDAP binds  
- Implement strong access controls  
- Enforce least privilege principles  
- Monitor unusual LDAP queries  
- Harden domain controller configurations  

---
