# 11 – Session Hijacking 🧩

## 📌 Lab Overview

This module focuses on session hijacking techniques used to take over authenticated user sessions by capturing or manipulating session identifiers.

Testing was performed on the Altoro Mutual test application (testfire.net) in a controlled lab environment.

---

## 🎯 Objectives

- Understand session hijacking concepts and lifecycle  
- Capture and analyze session IDs  
- Perform session hijacking using multiple techniques  
- Evaluate session security weaknesses  
- Understand mitigation strategies  

---

## 🧠 Types of Session Hijacking

- **Active Hijacking** – Attacker takes over an active session  
- **Passive Hijacking** – Attacker monitors session traffic  
- **Session Fixation** – Forcing a user to use a known session ID  
- **MITM-Based Hijacking** – Intercepting communication between client and server  
- **XSS-Based Hijacking** – Stealing session cookies via script injection  

---

## 🔁 Session Hijacking Lifecycle

1. Target Identification  
2. Session ID Acquisition  
3. Session Takeover  
4. Exploitation  

---

## 🛠 Tools Used

- Wireshark  
- Burp Suite  
- Ettercap  
- Bettercap  
- BeEF (Browser Exploitation Framework)  
- Cookie Cadger  
- Cain & Abel  

---

## 🔍 Methodology

### 📡 Session Hijacking using Wireshark

Wireshark was used to capture network traffic and analyze session cookies transmitted over the network.

Observed:

- HTTP session identifiers  
- Unencrypted traffic exposure  
- Cookie transmission patterns  

---

### 🧪 Testing Session ID Predictability using Burp Suite

Burp Suite Sequencer was used to analyze session token randomness.

Purpose:

- Identify weak session ID generation  
- Detect predictable session tokens  

---

### ⚠️ Session Hijacking using Ettercap

Ettercap was used to perform MITM attacks and intercept session data.

Capabilities:

- ARP poisoning  
- Packet interception  
- Credential capture  

---

### 🧬 Session Hijacking using Bettercap

Bettercap was used to automate MITM attacks and session interception.

Features:

- Traffic sniffing  
- Session capture  
- Network manipulation  

---

### 🍪 Manual Cookie Theft

Session cookies were manually extracted and reused to hijack sessions.

Process:

- Capture session cookie  
- Inject cookie into browser  
- Access authenticated session  

This demonstrated real-world session hijacking scenarios.

---

## 🔧 Session Hijacking Techniques

- Sniffing  
- Cross-Site Scripting (XSS)  
- Session Fixation  
- Man-in-the-Middle (MITM)  
- Brute Force  
- Trojan-based attacks  

---

## 📊 Findings

- Session IDs transmitted over insecure channels  
- Weak session token randomness detected  
- Successful session takeover using captured cookies  
- MITM attacks enabled interception of authentication data  

---

## ⚠️ Risk Analysis

Session hijacking may lead to:

- Unauthorized account access  
- Data theft  
- Privilege escalation  
- Financial fraud  
- Full session compromise  

Poor session management significantly increases risk.

---

## 🛡 Mitigation Recommendations

- Use HTTPS for all communications  
- Implement secure cookie attributes (HttpOnly, Secure)  
- Use strong session ID generation  
- Implement session expiration and timeout  
- Use multi-factor authentication  
- Monitor session anomalies  

---

## 📝 Lab Outcome

Developed practical understanding of session management vulnerabilities, session hijacking techniques, and defensive controls required to secure web application sessions.
