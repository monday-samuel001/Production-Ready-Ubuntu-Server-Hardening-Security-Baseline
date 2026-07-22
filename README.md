<p align="center">
  <img src="assets/github-banner.png" alt="Production-Ready Ubuntu Server Hardening & Security Baseline Banner">
</p>

# 🛡️ Production-Ready Ubuntu Server Hardening & Security Baseline

![Ubuntu](https://img.shields.io/badge/Ubuntu-22.04-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-Security-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![OpenSSH](https://img.shields.io/badge/OpenSSH-Hardened-success?style=for-the-badge)
![UFW](https://img.shields.io/badge/UFW-Firewall-blue?style=for-the-badge)
![Fail2Ban](https://img.shields.io/badge/Fail2Ban-Intrusion%20Prevention-red?style=for-the-badge)
![Auditd](https://img.shields.io/badge/Auditd-Security%20Auditing-orange?style=for-the-badge)
![Documentation](https://img.shields.io/badge/Documentation-Complete-brightgreen?style=for-the-badge)

## Project Overview

This project demonstrates the implementation of a **production-oriented Ubuntu Server Hardening & Security Baseline** using layered security controls aligned with industry security best practices.

Rather than simply applying Linux hardening commands, every security control was **implemented, validated, and documented** using real configuration evidence and verification testing. Each chapter of the project demonstrates not only how a security control was configured, but also how its effectiveness was confirmed through practical validation.

The project follows a **Defense-in-Depth** approach, combining secure authentication, access control, logging and auditing, file integrity protection, system maintenance, network security, and intrusion prevention into a single security baseline designed to reduce risk and improve overall system resilience.

The repository serves as both a technical implementation guide and a portfolio project, demonstrating practical Linux security engineering, structured documentation, and production-oriented operational thinking.

## ✨ Project Highlights

- 🛡️ Production-oriented Ubuntu Server hardening
- 🔐 Layered Defense-in-Depth security architecture
- ✅ Real configuration evidence with validation testing
- 📖 Seven structured security domains
- 📸 Configuration screenshots for every implemented control
- 🏗️ Professional security architecture documentation
- 📚 Comprehensive technical documentation

---

## 🏗️ Security Architecture

The security baseline follows a layered **Defense-in-Depth** architecture, where multiple independent security controls work together to reduce risk, strengthen authentication, improve system visibility, and protect the server against common attack techniques.

Rather than relying on a single security mechanism, the architecture combines authentication, access control, monitoring, integrity protection, system maintenance, network security, and intrusion prevention into a unified security model.

<p align="center">
  <img src="architecture/ubuntu-server-security-architecture.png" alt="Production Ubuntu Server Security Architecture" width="1000">
</p>

---

## 🔐 Security Controls Implemented

| Security Domain          | Controls Implemented |
|--------------------------|----------------------|
| **Authentication**       | SSH Hardening, SSH Key Authentication, Disable Password Authentication, Google MFA, Disable Root Login |
| **Access Control**       | User & Group Management, Principle of Least Privilege, Custom sudo Policies |
| **Logging & Auditing**   | NGINX Access Logs, Auditd Monitoring, Security Event Auditing |
| **File Integrity**       | Immutable Files, Append-Only Logs |
| **System Maintenance**   | Automatic Security Updates, Patch Management |
| **Network Security**     | UFW Firewall, Default-Deny Firewall Policy, Firewall Validation |
| **Intrusion Prevention** | Fail2Ban SSH Protection |

---

## ✅ Validation Methodology

Every implemented security control was independently validated to confirm that it functioned as intended.

The validation process included:

- Configuration verification
- Functional testing
- Security validation
- Real-world attack simulations where appropriate
- Supporting screenshots captured from the implementation environment

This evidence-based approach demonstrates not only how each control was configured, but also how its effectiveness was verified using practical testing.

---

## 📂 Repository Structure

```text
Production-Ready-Ubuntu-Server-Hardening-Security-Baseline/

├── architecture/
│   ├── ubuntu-server-security-architecture.drawio
│   ├── ubuntu-server-security-architecture.png
│   └── ubuntu-server-security-architecture.svg
│
├── configs/
│
├── docs/
│   ├── 01-authentication.md
│   ├── 02-access-control.md
│   ├── 03-logging-and-auditing.md
│   ├── 04-file-integrity.md
│   ├── 05-system-maintenance.md
│   ├── 06-network-security.md
│   ├── 07-intrusion-prevention.md
│   └── project-summary.md
│
├── screenshots/
│
└── README.md

## 📖 Documentation Guide

The complete implementation is documented across seven security domains.

| Document | Description |
|----------|-------------|
| `01-authentication.md` | SSH hardening, SSH keys, MFA, password authentication, root login |
| `02-access-control.md` | User management, groups, least privilege, custom sudo policies |
| `03-logging-and-auditing.md` | NGINX logging, Auditd configuration, security monitoring |
| `04-file-integrity.md` | Immutable files and append-only log protection |
| `05-system-maintenance.md` | Automatic security updates and patch management |
| `06-network-security.md` | UFW firewall configuration and validation |
| `07-intrusion-prevention.md` | Fail2Ban configuration and brute-force protection |
| `project-summary.md` | Complete project overview and engineering summary |
