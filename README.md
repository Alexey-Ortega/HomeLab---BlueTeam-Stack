Here's your README fully translated to English:

---

# 🛡️ Blue Team Homelab

> Complete virtualization infrastructure for learning defensive cybersecurity (Blue Team), digital forensics, and security operations.

---

## 📋 Description

This repository documents the design, configuration, and lessons learned from a cybersecurity homelab built on consumer-grade hardware (HP laptop, Intel Core i7 7th gen, 16GB RAM, 620GB storage).

The primary goal is to develop hands-on skills in:
- Blue Team operations
- Log analysis and threat detection with SIEM
- Digital forensics analysis
- Linux systems administration
- Virtualization and infrastructure management

---

## 🏗️ Architecture

*(keep the diagram as-is, it's already visual)*

---

## 💻 Hardware

| Component | Specification |
|-----------|---------------|
| CPU | Intel Core i7 7th Generation |
| RAM | 16 GB DDR4 |
| Storage | 520 GB NVMe (OS + VMs) |
| Storage 2 | 1 TB HDD (data) |
| Network | Gigabit Ethernet |
| UPS | Battery backup for power outage protection |

---

## 🖥️ Virtual Machines

### VM 100 — Debian + Docker (Web/App Server)
- **OS:** Debian 13 (Trixie)
- **Resources:** 4 vCPU, 6 GB RAM, 120 GB disk
- **Services:** Nginx, Docker Engine, Portainer CE
- **Status:** Always on

### VM 101 — Windows 10 Lab (Victim environment)
- **OS:** Windows 10 64-bit
- **Resources:** 2 vCPU, 4 GB RAM, 65 GB disk
- **Purpose:** Isolated environment for attack simulations
- **Status:** On-demand

### VM 102 — SIFT Workstation (Digital Forensics)
- **OS:** Ubuntu 22.04 LTS (SIFT base)
- **Resources:** 2 vCPU, 2 GB RAM, 50 GB disk
- **Tools:** 80+ forensic tools from the SANS Institute
- **Status:** On-demand

### VM 103 — Elastic SIEM (Operations Center)
- **OS:** Ubuntu 22.04 LTS
- **Resources:** 3 vCPU, 4 GB RAM, 120 GB disk
- **Stack:** Elasticsearch 8.x + Kibana 8.x
- **Status:** Always on

---

## 🔒 Security Implemented

- UFW Firewall with minimal required rules
- Fail2ban for brute-force protection
- SSH authentication via ED25519 keys (no passwords)
- VMs segmented by function

---

## 🎯 Roadmap

- [x] Proxmox VE installed and configured
- [x] Debian VM with Docker and Portainer
- [x] Security hardening (UFW, Fail2ban, SSH keys)
- [x] Windows 10 VM for attack testing
- [x] SIFT Workstation for forensics
- [x] Elastic SIEM (Elasticsearch + Kibana)
- [ ] Wazuh agents on VMs
- [ ] TrueNAS for NAS storage
- [ ] Cloudflare Tunnel for secure external access
- [ ] Custom Kibana dashboards

---

## ⚠️ Security Notes

- No IPs, credentials, tokens, or sensitive information included
- Sensitive configurations use environment variables (excluded via .gitignore)
- Victim VMs are isolated from the main network

---

*Built for educational purposes to develop defensive cybersecurity skills.*

---
