# 🛡️ Blue Team Homelab

![Proxmox](https://img.shields.io/badge/Proxmox-VE_8-E57000?style=flat&logo=proxmox)
![Elastic](https://img.shields.io/badge/Elastic-SIEM_8.x-005571?style=flat&logo=elastic)
![Docker](https://img.shields.io/badge/Docker-Engine-2496ED?style=flat&logo=docker)
![Status](https://img.shields.io/badge/Status-Active-success?style=flat)
![Focus](https://img.shields.io/badge/Focus-Blue_Team-blue?style=flat)

> Complete virtualization infrastructure for hands-on defensive cybersecurity training — covering SIEM/SOC operations, digital forensics, and brute-force attack simulations.

---

## 🧠 Why This Lab?

I built this homelab to bridge the gap between theory and real-world Blue Team work. Instead of just reading about threat detection or forensics, I wanted an environment where I could actually break things, detect them, and respond — all on my own hardware.

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

    ┌─────────────────────────────────────────────────────────────┐
    │                     PROXMOX VE 8.x                          │
    │                  (Bare-metal Hypervisor)                     │
    │                                                              │
    │  ┌──────────────┐  ┌──────────────┐  ┌────────────────────┐ │
    │  │   VM 100     │  │   VM 101     │  │      VM 102        │ │
    │  │ Debian +     │  │ Windows 10   │  │ SIFT Workstation   │ │
    │  │ Docker       │  │ Lab (victim) │  │ (SANS Forensics)   │ │
    │  │ 4vCPU/6GB    │  │ 2vCPU/4GB    │  │ 2vCPU/2GB          │ │
    │  └──────────────┘  └──────────────┘  └────────────────────┘ │
    │                                                              │
    │  ┌──────────────────────────────────────────────────────┐   │
    │  │                      VM 103                          │   │
    │  │                  Elastic SIEM                        │   │
    │  │         (Elasticsearch + Kibana + Logstash)          │   │
    │  │                   3vCPU / 4GB RAM                    │   │
    │  └──────────────────────────────────────────────────────┘   │
    └─────────────────────────────────────────────────────────────┘

---

## 💻 Hardware

| Component | Specification |
|---|---|
| CPU | Intel Core i7 7th Generation |
| RAM | 16 GB DDR4 |
| Storage (main) | 520 GB NVMe (OS + VMs) |
| Storage (data) | 1 TB HDD |
| Network | Gigabit Ethernet |
| UPS | Battery backup for power protection |

---

## 🖥️ Virtual Machines

### VM 100 — Debian + Docker (Web/App Server)
- **OS:** Debian 13 (Trixie)
- **Resources:** 4 vCPU · 6 GB RAM · 120 GB disk
- **Services:** Nginx, Docker Engine, Portainer CE
- **Status:** Always on

### VM 101 — Windows 10 Lab (Victim Machine)
- **OS:** Windows 10 64-bit
- **Resources:** 2 vCPU · 4 GB RAM · 65 GB disk
- **Purpose:** Isolated environment for attack simulations
- **Status:** On-demand

### VM 102 — SIFT Workstation (Digital Forensics)
- **OS:** Ubuntu 22.04 LTS (SIFT base)
- **Resources:** 2 vCPU · 2 GB RAM · 50 GB disk
- **Tools:** 80+ forensic tools from the SANS Institute
- **Status:** On-demand

### VM 103 — Elastic SIEM (Operations Center)
- **OS:** Ubuntu 22.04 LTS
- **Resources:** 3 vCPU · 4 GB RAM · 120 GB disk
- **Stack:** Elasticsearch 8.x + Kibana 8.x
- **Status:** Always on

---

## 🔒 Security Implemented

- UFW Firewall with minimal required rules
- Fail2ban for brute-force attack protection
- SSH key-based authentication via ED25519 (no passwords)
- VMs network-segmented by function

---

## 🎯 Roadmap

- [x] Proxmox VE installed and configured
- [x] Debian VM with Docker and Portainer
- [x] Security hardening (UFW, Fail2ban, SSH keys)
- [x] Windows 10 VM for attack simulation
- [x] SIFT Workstation for digital forensics
- [x] Elastic SIEM (Elasticsearch + Kibana)
- [ ] Wazuh agents deployed on all VMs
- [ ] TrueNAS for centralized NAS storage
- [ ] Cloudflare Tunnel for secure external access
- [ ] Custom detection dashboards in Kibana

---

## ⚠️ Security Notes

- No IPs, credentials, tokens, or sensitive data included
- Sensitive configurations use environment variables (excluded via `.gitignore`)
- Victim VMs are fully isolated from the main network

---

*Built for educational purposes — developing real-world defensive cybersecurity skills, one incident at a time.*
