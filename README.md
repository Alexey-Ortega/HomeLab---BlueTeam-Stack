# 🛡️ Blue Team Homelab – SOC & Threat Detection Lab

**Laboratorio profesional de ciberseguridad defensiva (Blue Team / SOC Analyst)**

![Proxmox](https://img.shields.io/badge/Proxmox-VE%209.1-brightgreen)
![Elastic](https://img.shields.io/badge/Elastic-Stack-005571)
![WireGuard](https://img.shields.io/badge/VPN-WireGuard-8811FF)
![Docker](https://img.shields.io/badge/Docker-Engine-2496ED)
![Status](https://img.shields.io/badge/Estado-Operativo-success)

---

### 🎯 Objetivo
Entorno realista y segmentado para practicar y demostrar competencias de **Blue Team / SOC Analyst**:

- Monitoreo y correlación de logs en tiempo real
- Detección y respuesta a amenazas (Threat Hunting)
- Análisis forense digital
- Simulación controlada de ataques
- Preparación para roles entry-level en Querétaro

---

### 🧱 Infraestructura

- **Hipervisor**: Proxmox VE 9.1.1
- **Hardware**: Intel Core i7 7th Gen | 16 GB RAM | NVMe + HDD
- **Redes segmentadas**:
  - `vmbr0` → Red principal (192.168.1.0/24)
  - `vmbr2` → Red aislada para pruebas de malware (10.10.10.0/24)

---

### 🖥️ Máquinas Virtuales (Estado actual)

| VMID | Nombre              | SO            | Estado | Rol principal                          |
|------|---------------------|---------------|--------|----------------------------------------|
| 100  | Debian-Docker       | Debian 13     | 🟢    | Servicios críticos (Docker, Portainer, WireGuard, Bot Telegram) |
| 103  | Elastic-Siem        | Ubuntu 22.04  | 🟢    | SIEM central (Kibana + Fleet Server)   |
| 8000 | Windows-Victim      | Windows 10/11 | 🟢    | Máquina de detonación de malware       |
| 404  | Linux-Victim        | Ubuntu        | 🔴    | Víctima Linux                          |
| 102  | SIFT                | Ubuntu        | 🔴    | Análisis forense (bajo demanda)        |

**VMs inamovibles (críticas)**: 100 y 103

---

### 🐳 Servicios Principales (VM 100)

- WireGuard → VPN remota segura
- Portainer → Gestión de Docker
- Bot Telegram → Alertas en tiempo real
- Nginx → Reverse proxy y dashboards

---

### 📊 SIEM – Elastic Stack

- Elasticsearch + Kibana (HTTPS)
- Fleet Server
- Elastic Agents en Proxmox y VMs críticas

**Flujo actual**:  
Proxmox + VMs → Elastic Agent → Fleet → Elasticsearch → Kibana

---

### 🔐 Hardening Aplicado

- Cortafuegos por capas
- Acceso SSH solo por llave
- Puertos mínimos expuestos
- Segmentación estricta (vmbr2 aislada)
- Snapshots regulares de VMs críticas

---

### 🧪 Escenarios de Práctica Activos

- Detección de escaneos y fuerza bruta
- Ejecución controlada de malware (LockBit 5.0, Lumma Stealer, AsyncRAT, Mirai)
- Análisis forense con SANS SIFT
- Creación y tuning de reglas de detección en Elastic

---

### 📦 Estructura del Repositorio

```bash
homelab-blue-team/
├── README.md
├── configs/          # Configuraciones sanitizadas
├── scripts/          # Automatización y alertas
├── docs/             # Reportes SOC y playbooks
├── diagrams/         # Diagramas y topología
└── snapshots/        # Backups de configuración
