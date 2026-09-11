# Infrastructure & Blue Team HomeLab

![Proxmox](https://img.shields.io/badge/Proxmox-VE-E57000?logo=proxmox&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-Debian%20%7C%20Ubuntu-FCC624?logo=linux&logoColor=black)
![Docker](https://img.shields.io/badge/Docker-Engine-2496ED?logo=docker&logoColor=white)
![Elastic](https://img.shields.io/badge/Elastic-Stack-005571?logo=elastic&logoColor=white)
![Status](https://img.shields.io/badge/status-active-success)

A hands-on environment for practicing **systems administration, virtualization, networking, monitoring, troubleshooting and defensive security**.

> This repository documents a personal lab. Internal addresses, credentials, tokens and other sensitive values are intentionally omitted.

## Purpose

This lab is designed to build practical skills for **Systems Administrator and IT Infrastructure roles**, with Blue Team monitoring as a complementary specialization.

The environment is used to practice:

- Linux server administration
- Virtual machine lifecycle management
- Docker service deployment and troubleshooting
- Remote administration through SSH and WireGuard
- Reverse proxy and service availability
- Centralized log collection and monitoring
- Network traffic visibility with Suricata
- Backups, snapshots and recovery planning

## Architecture

```text
                         Proxmox VE
                              |
          +-------------------+-------------------+
          |                   |                   |
   Debian services      Elastic monitoring     Test systems
          |                   |                   |
 Docker / Nginx         Fleet / Kibana       Linux / Windows
 WireGuard / tools      Logs / alerts        Troubleshooting
```

## Core Components

### Virtualization

- Proxmox VE as the hypervisor
- Debian and Ubuntu virtual machines
- Isolated test systems for controlled lab exercises
- Snapshots before significant configuration changes

### Services and Remote Administration

- Docker Engine for containerized services
- Nginx as a reverse proxy
- WireGuard for secure remote access
- SSH administration with key-based authentication
- Portainer for container visibility and management

### Monitoring and Security

- Elasticsearch and Kibana for centralized visibility
- Fleet Server and Elastic Agents for log collection
- Suricata for network monitoring on the Linux test system
- Log review and filtering with command-line tools
- Controlled Nmap scans to validate network detections

## Current Progress

- [x] Deploy Proxmox and Linux virtual machines
- [x] Run containerized infrastructure services
- [x] Configure remote administration
- [x] Deploy Elastic Stack and Fleet Server
- [x] Connect and validate Elastic Agents
- [x] Generate and review Suricata events
- [x] Validate visibility with a controlled network scan
- [ ] Document backup and restore procedures
- [ ] Add Windows Server and Active Directory scenarios
- [ ] Add sanitized configuration examples
- [ ] Create incident notes and troubleshooting runbooks
- [ ] Improve dashboards and alerting

## Skills Demonstrated

`Linux Administration` · `Proxmox` · `Docker` · `Networking` · `SSH` · `Nginx` · `WireGuard` · `Elastic Stack` · `Suricata` · `Troubleshooting` · `Security Hardening`

## Repository Status

This repository currently focuses on documentation. Sanitized configurations, diagrams and operational notes will be added as the lab develops.

## Author

**Alexei Cuevas Ortega**

Systems Engineering student focused on **Systems Administration, IT Infrastructure and Blue Team fundamentals**.

- [GitHub profile](https://github.com/Alexey-Ortega)
- [LinkedIn](https://www.linkedin.com/in/alexei-cuevas-9a39552a7/)
