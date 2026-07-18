# SkillsQuark – Network Security Engineering Internship
## Task 1: Network Mapping

**Submitted by:** Habiba Shafait
**Organization:** SkillsQuark
**Internship Program:** Network Security Engineering Internship
**Tool Used:** Nmap 7.99
**Submission Date:** 03 July 2026

---

## 1. Objective

The objective of this task is to understand and apply the concept of network mapping using the Nmap network scanning tool. Network mapping is a foundational skill in cybersecurity that allows a security engineer to build a clear picture of the devices, services, and communication paths present within a network.

This task focuses on performing host discovery, TCP port scanning, and UDP port scanning on a local Wi-Fi network using Nmap 7.99, and on interpreting the results from a security perspective.

## 2. Introduction

Network mapping is the process of discovering the devices connected to a network and identifying how they communicate with one another. It is one of the earliest and most important steps in any network security assessment, penetration test, or IT audit, because it establishes visibility into what actually exists on a network before any further analysis can take place.

By discovering active hosts, scanning for open ports, and identifying the services bound to those ports, a security engineer can:

- Build an accurate and up-to-date inventory of network assets
- Detect unauthorized or unknown devices connected to the network
- Identify unnecessary or risky open services that increase the attack surface
- Prioritize which hosts and services require closer security review
- Establish a baseline for ongoing network monitoring

## 3. Tools Used

- **Nmap 7.99** – open-source network scanning tool used for host discovery, port scanning, and service detection
- **Windows Command Prompt** – used to execute Nmap commands and view scan output
- **Windows Operating System** – host OS on which Nmap was installed and executed

## 4. Environment Setup

- A Windows laptop connected to a local Wi-Fi network
- Nmap 7.99 installed and verified successfully on the system
- Local IPv4 address of the scanning machine: `192.168.100.12`
- Target network range for scanning: `192.168.100.0/24` (256 addresses)

---

## Step-by-Step Procedure

### Step 1 — Verify Nmap Installation

```bash
nmap --version
```

Confirms Nmap is installed correctly and displays the version and compiled libraries in use.

---

### Step 2 — Check Local IP Configuration

```bash
ipconfig
```

Displays the machine's TCP/IP configuration, used here to identify the scanning machine's IP address (`192.168.100.12`) and determine the correct network range to scan.

---

### Step 3 — Host Discovery Scan

```bash
nmap -sn 192.168.100.0/24
```

Performs a "ping scan" across the whole `/24` range to determine which hosts are online, without scanning ports. **Result: 5 active hosts found** out of 256 addresses.

---

### Step 4 — TCP Port Scan

```bash
nmap 192.168.100.12
```

Scans the 1,000 most common TCP ports on the target host and reports open ports with their likely services.

**Open TCP ports found:** 135 (msrpc), 139 (netbios-ssn), 445 (microsoft-ds), 2179 (vmrdp), 3306 (mysql), 5357 (wsdapi)

---

### Step 5 — UDP Port Scan

```bash
nmap -sU 192.168.100.12
```

Performs a UDP scan to discover services (like DNS, DHCP, NetBIOS) that run over UDP and wouldn't appear in a TCP scan.

**Open/filtered UDP ports found:** 137 (netbios-ns), 138 (netbios-dgm), 1900 (upnp/ssdp), 3702 (ws-discovery), 4500 (nat-t-ike), 5050, 5353 (mdns), 5355 (llmnr)

---

## Asset Inventory

| IP Address | Device Type | Status | Notes |
|---|---|---|---|
| 192.168.100.1 | Router (Gateway) | Up | Huawei router; default gateway |
| 192.168.100.9 | Unidentified Host | Up | Further identification recommended |
| 192.168.100.12 | Laptop (Scanning Host) | Up | Device used to perform all scans |
| 192.168.100.30 | Unidentified Host | Up | Further identification recommended |
| 192.168.100.33 | Unidentified Host | Up | Further identification recommended |

## TCP Port Analysis

| Port | Service | Security Relevance |
|---|---|---|
| 135 | MSRPC | Windows RPC endpoint mapper; frequently targeted by malware/worms |
| 139 | NetBIOS-SSN | Legacy file/printer sharing; known weaknesses |
| 445 | Microsoft-DS | SMB over TCP/IP; exploited in major ransomware attacks (e.g., WannaCry) |
| 2179 | VMRDP | Hyper-V remote console access to VMs |
| 3306 | MySQL | Database service; risk if exposed without proper access control |
| 5357 | WSDAPI | Windows device discovery (printers, media sharing) |

## UDP Port Analysis

| Port | Service | Security Relevance |
|---|---|---|
| 137 | NetBIOS Name Service | Legacy name resolution, often enabled by default |
| 138 | NetBIOS Datagram Service | Connectionless NetBIOS file/printer sharing |
| 1900 | SSDP | UPnP device advertisement |
| 3702 | WS-Discovery | Windows auto-discovery of printers/scanners |
| 4500 | IPSec NAT-T | IPSec VPN traffic traversal across NAT |
| 5050 | Unassigned/App-specific | Requires further investigation |
| 5353 | mDNS | Multicast DNS / local device discovery (Bonjour) |
| 5355 | LLMNR | Legacy name resolution; vulnerable to spoofing/relay attacks |

## Findings

| Metric | Result |
|---|---|
| Total IP addresses scanned | 256 (192.168.100.0/24) |
| Active hosts found | 5 |
| Open TCP ports (192.168.100.12) | 135, 139, 445, 2179, 3306, 5357 |
| Open/Filtered UDP ports (192.168.100.12) | 137, 138, 1900, 3702, 4500, 5050, 5353, 5355 |

Out of the full 256-address range, only 5 hosts responded as active — a small, lightly populated network with a gateway router, the scanning laptop, and a few other connected devices. The scanning host exposed standard Windows networking ports plus one database port (3306), which should be reviewed to confirm whether MySQL needs to remain network-accessible.

## Conclusion

This task provided practical, hands-on experience with network mapping using Nmap 7.99. Through host discovery, TCP scanning, and UDP scanning, it was possible to build a clear picture of the devices and services active on a local network segment.

Network mapping is a critical first step in any security assessment because it establishes visibility into what is actually present on a network. Regular network mapping supports asset management, strengthens an organization's security baseline, and forms the foundation for more advanced activities such as vulnerability scanning and penetration testing.

## References

1. Nmap Official Website – https://nmap.org
2. Official Nmap Documentation and Reference Guide
