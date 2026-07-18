# 🔥 Firewall Policy Design using iptables

This project demonstrates the design, implementation, and verification of a secure firewall policy using **iptables** in a Linux environment. The firewall configuration was tested using multiple security tools to ensure that only authorized services remained accessible while unnecessary ports were blocked.

---

## 📌 Project Overview

The objective of this project is to protect a web server from unauthorized network access while allowing legitimate traffic required for normal operation.

The firewall policy was designed using **iptables** and verified using multiple penetration testing and network analysis tools.

---

## 🎯 Objectives

- Design a secure firewall policy.
- Allow only required services.
- Block insecure and unnecessary ports.
- Verify firewall behavior using multiple tools.
- Document the complete implementation process.

---

## 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| Kali Linux | Security Testing Platform |
| iptables | Firewall Configuration |
| Nmap | Port Scanning |
| curl | HTTP Service Verification |
| Netcat (nc) | TCP Connectivity Testing |
| Metasploit Framework | Port Scan Verification |

---

## 🔐 Firewall Policy

### Allowed Ports

| Port | Service |
|------|---------|
|22|SSH|
|80|HTTP|

### Blocked Ports

| Port | Service |
|------|---------|
|23|Telnet|
|443|HTTPS|

---

## 📋 Firewall Rules

```bash
iptables -A INPUT -p tcp --dport 22 -j ACCEPT

iptables -A INPUT -p tcp --dport 80 -j ACCEPT

iptables -A INPUT -p tcp --dport 23 -j REJECT

iptables -A INPUT -p tcp --dport 443 -j REJECT

iptables -P INPUT DROP
```

---

## 🔄 Verification Methods

- Nmap Scan
- curl HTTP Test
- Netcat Connection Test
- Metasploit TCP Port Scan

---

## 📂 Repository Contents

```
README.md
Task3_Firewall_Policy_Report.pdf
Task3_Firewall_Screenshots.pdf
```

---

## 📄 Report

The detailed report explains:

- Firewall Policy Design
- Rule Implementation
- Testing Methodology
- Verification Results
- Final Hardened Configuration

---

## ⚠️ Disclaimer

This project was performed in a controlled virtual lab environment for educational purposes only.

---

## 👩‍💻 Author

**Habiba Shafait**

BS Information Technology

Government College Women University, Sialkot
