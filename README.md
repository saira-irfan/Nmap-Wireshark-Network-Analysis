# 🔍 Nmap & Wireshark — Network Security Analysis

> Hands-on network reconnaissance and traffic analysis project  
> performed in an isolated VMware virtual lab environment.

**Course:** CY2004 Cyber Security | **University:** FAST-NUCES Islamabad  
**Team:** Saira Irfan (24i-2125) & Roshni Fawad (23i-2107)

---

## 📌 Overview
This project simulates real-world attacker and defender techniques 
using Nmap for network scanning and Wireshark for packet analysis. 
All tests were conducted safely inside a private virtual network 
with no external systems involved.

---

## 🛠️ Tools & Environment
| Tool | Purpose |
|------|---------|
| Nmap 7.95 | Host discovery, port scanning, OS detection |
| Wireshark 4.6 | Packet capturing and traffic analysis |
| Kali Linux | Security testing platform (Guest VM) |
| VMware Workstation | Virtual lab isolation |
| Windows 11 | Target machine (Host) |

---

## 🌐 Network Setup
   Host (Windows 11)   →   192.168.23.1
   Guest (Kali Linux)  →   192.168.23.129
   Subnet              →   192.168.23.0/24
   Network Type        →   Host-Only (VMnet1)


---

## 📂 Project Report
📄 Full detailed report with screenshots and analysis:  
👉 [View Report](./Nmap-Wireshark-Security-Analysis-Report.pdf)

---

## ✅ Key Results
| Scan Type | Command | Finding |
|-----------|---------|---------|
| Host Discovery | `nmap -sn 192.168.23.0/24` | 4 hosts alive |
| TCP Connect | `nmap -sT 192.168.23.1` | Ports 135, 139, 445 open |
| SYN Stealth | `nmap -sS 192.168.23.1` | Same, less noisy |
| Full Port | `nmap -p- 192.168.23.1` | No hidden ports found |
| Version Detection | `nmap -sV 192.168.23.1` | HTTP version 4.x detected |
| OS Detection | `nmap -O 192.168.23.1` | Inconclusive (ports filtered) |
| EternalBlue Check | `nmap --script smb-vuln-ms17-010 -p 445` | Port filtered ✅ |

---

## 🔒 Security Conclusion
All critical ports were filtered by Windows Firewall — the system 
showed a strong security posture with minimal exposed attack surface.
