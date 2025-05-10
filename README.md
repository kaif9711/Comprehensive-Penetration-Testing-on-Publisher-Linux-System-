# Comprehensive-Penetration-Testing-on-Publisher-Linux-System-
Penetration testing of a vulnerable Linux-based Publisher VM using Nmap, OpenVAS, SPIP RCE, and privilege escalation techniques with tools like Burp Suite, Hydra, and Metasploit.
# Comprehensive Penetration Testing on Publisher (Linux System)

## 🔍 Overview
This project is a full-scale penetration test conducted on a vulnerable Linux-based virtual machine named **Publisher**. The system hosted a SPIP CMS instance and other exploitable services, providing a real-world simulation of attack surfaces. The test was performed as part of a cybersecurity lab using Kali Linux as the attacker machine and OPNSense as a firewall.

## 🧰 Tools Used
- **Scanning & Recon:** Nmap, OpenVAS, Netdiscover, WhatWeb, Enum4linux
- **Exploitation:** Metasploit, Burp Suite, Hydra, Gobuster, ffuf, SPIP RCE exploit
- **Privilege Escalation:** LinPEAS, SUID misconfiguration, AppArmor bypass
- **Password Cracking:** John the Ripper
- **Monitoring:** Wireshark
- **CMS Auditing:** SPIP enumeration and SQLMap

## 🔑 Key Findings
| Service | Vulnerability | Severity | CVE |
|--------|---------------|----------|-----|
| SSH (Port 22) | Weak MAC algorithm | Low | N/A |
| HTTP (Port 80) | SPIP Remote Code Execution (RCE) | High | CVE-2020-26870 |
| TCP / ICMP | Timestamp Info Disclosure | Low | CVE-2000-0649 |
| Apache | Missing security headers, directory listing | Medium | CVE-2000-0649 |

## ⚔️ Exploitation Summary
- **Brute-force SSH** login using Hydra and Metasploit
- **SPIP RCE** using a custom Python exploit (verified shell access)
- **Privilege escalation** using misconfigured SUID binary `/opt/run_container.sh` and AppArmor bypass via `/bin/bash -p`
- **Accessed private SSH keys** in `/home/think/.ssh/id_rsa` for lateral movement
- **Post-exploitation enumeration** with LinPEAS

## 📄 Report Contents
The full PDF report includes:
- Setup and network topology
- Vulnerability discovery using OpenVAS and Nmap scripts
- Directory brute-forcing via Gobuster and ffuf
- Privilege escalation workflow (SUID abuse, container scripts)
- Failed and successful SQL injection attempts via Burp Suite and SQLMap
- Meterpreter session gain and shell interactions

## 📁 Files in This Repo
- `Comprehensive Penetration Testing on Publisher (Linux System).pdf`: Full pentest report with methodology, tools, screenshots, and exploits used
- `README.md`: Summary and project breakdown

## 📌 Disclaimer
This project was conducted in a safe, academic lab environment for educational purposes only. All tools and techniques were applied ethically on simulated systems.

---

> 🛡️ *Project by Mohammad Kaif as part of Cybersecurity training lab.*
