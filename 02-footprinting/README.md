# 02 – Footprinting 🔎

## 📌 Lab Overview

This module focuses on footprinting techniques used to gather intelligence about a target organization before launching active attacks. The objective is to identify publicly available information that can expand the attack surface.

Both passive and controlled reconnaissance techniques were performed.

---

## 🎯 Objectives

- Gather domain registration details  
- Identify IP address information  
- Discover subdomains  
- Enumerate publicly exposed email addresses  
- Analyze search engine exposure using Google Dorking  

---

## 🛠 Tools & Techniques Used

- Google Dorking  
- Google Hacking Database (GHDB)  
- WHOIS  
- theHarvester  
- ShellGPT (for generating Google dorks)  

---

## 🔍 Methodology

### 🌐 1. Google Dorking

Advanced Google search operators were used to discover exposed information.

Examples:

site:certifiedhacker.com

site:filetype:pdf Penetration tester 3rd edition

intitle:"index of"

---

Google Hacking Database (GHDB) queries were reviewed to identify potentially sensitive publicly accessible resources.

---

### 🤖 2. Google Dorks via ShellGPT

ShellGPT was used to generate optimized Google dork queries to discover:

- Publicly indexed files  
- Login portals  
- Configuration files  
- Email addresses  

This helped automate structured reconnaissance queries.

---

### 🧾 3. WHOIS Lookup

Used to gather domain registration details such as:

- Registrar information  
- Registration dates  
- Name servers  
- Administrative contact details  

Example command:

whois certifiedhacker.com

---


Information collected:

- Email addresses  
- Subdomains  
- Hostnames  
- IP associations  

---

## 📊 Findings

- Identified domain registration metadata  
- Discovered multiple subdomains  
- Enumerated publicly exposed email addresses  
- Identified publicly accessible indexed files  
- Mapped initial external attack surface  

---

## ⚠️ Risk Analysis

Publicly exposed information may enable:

- Targeted phishing campaigns  
- Credential harvesting attempts  
- Infrastructure reconnaissance  
- Social engineering attacks  

Extensive OSINT reduces the effort required for attackers during later exploitation phases.

---

## 🛡 Mitigation Recommendations

- Limit publicly exposed sensitive files  
- Monitor search engine indexing  
- Remove unnecessary indexed directories  
- Use privacy protection for domain registration  
- Conduct periodic OSINT audits  

---

## 📝 Lab Outcome

Developed structured intelligence gathering skills using search engine reconnaissance, domain enumeration, and OSINT-based attack surface mapping techniques.
