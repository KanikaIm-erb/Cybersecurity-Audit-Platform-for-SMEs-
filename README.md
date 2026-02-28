<div align="center">
<!-- Banner -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,50:203a43,100:2c5364&height=200&section=header&text=🛡️%20Automated%20Security%20Audit%20Platform&fontSize=28&fontColor=ffffff&fontAlignY=38&desc=of%20Small%20%26%20Medium-sized%20Enterprises%20(SMEs)&descAlignY=58&descColor=a8dadc" width="100%"/>
<br/>

![Status](https://img.shields.io/badge/Status-In%20Development-orange?style=for-the-badge&logo=github)
![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Security](https://img.shields.io/badge/Focus-Cybersecurity-red?style=for-the-badge&logo=shield&logoColor=white)

<br/>

</div>

---

## 📚 Table of Contents

- [📖 Overview](#-overview)
- [ Problem Statement](#️-problem-statement)
- [ Key Features](#-key-features)
  - [📊 Dashboard & Reporting](#-dashboard--reporting)
  - [🗂️ Asset Registration & Management](#️-asset-registration--management)
  - [🔍 Network Scans](#-network-scans)
  - [🌐 Web Scans](#-web-scans)
  - [🛢️ Database Scans](#️-database-scans)
  - [⚙️ Configuration File Scans](#️-configuration-file-scans)
- [🛠️ Tools & Technology](#️-tools--technology)
- [🚧 Further Work (In Progress)](#-further-work-in-progress)
- [ Credits ](#-credits--acknowledgements)

---

## 📖 Overview

The **Automated Security Audit Platform for SMEs** is an open-source, end-to-end security auditing solution designed specifically for Small and Medium-sized Enterprises (SMEs). It orchestrates a suite of industry-standard open-source tools to automatically scan, assess, and report on an organisation's security posture.

Unlike expensive enterprise security suites, this platform brings together the best free and open-source tools into a unified, easy-to-deploy pipeline — making robust cybersecurity accessible to organisations with limited IT resources and budgets.

---

## Problem Statement

> *Small and medium-sized enterprises account for over **43% of all cybercrime targets** globally, yet most lack the resources to conduct regular, comprehensive security audits.*

**The core challenges SMEs face:**

-  **Cost** — Professional penetration testing and security audits can cost thousands per engagement
-  **Expertise Gap** — SMEs rarely employ dedicated security professionals
-  **Time** — Manual audits are slow, inconsistent, and rarely repeated
-  **Visibility** — Without continuous scanning, vulnerabilities go undetected for months
-  **Reporting** — Raw tool outputs are complex and not actionable for non-technical stakeholders

This platform addresses all of the above by providing an **automated, repeatable, and report-ready** security audit pipeline tailored for the SME threat landscape.

---

##  Key Features

### 📊 Dashboard & Reporting

**What it does:** Provides a centralised, visual interface to monitor the organisation's overall security posture, track scan history, and generate actionable reports for both technical and non-technical audiences.

**What it includes:**
- Real-time security score and risk overview across all assets
- Categorised findings view — Critical / High / Medium / Low / Informational
- Per-finding remediation guidance and recommendations
- Historical trend comparison between scan runs
- Role-based views: Executive Summary vs. Technical Deep-Dive
- Export formats: **PDF**, **HTML**, **JSON**, **CSV**

**Tools & Tech:** `Flask` / `Streamlit`, `Jinja2`, `WeasyPrint`, `Chart.js`, `ReportLab`

---

### 🗂️ Asset Registration & Management

**What it does:** Serves as the inventory backbone of the platform — allowing users to register, categorise, and manage all digital assets before and between scans, ensuring full audit coverage with no blind spots.

**What it manages:**
- Registration of IP addresses, hostnames, domains, and URL endpoints
- Asset tagging by type: servers, workstations, web apps, databases, network devices
- Asset grouping and prioritisation for targeted or scheduled scans
- Ownership and contact mapping per asset
- Auto-discovery of new assets detected during network scans
- Scan scheduling and assignment per asset or asset group

**Tools & Tech:** `SQLite` / `PostgreSQL`, `SQLAlchemy`, `Flask-Admin`, custom Python asset manager

---

### 🔍 Network Scans

**What it does:** Discovers all live hosts, open ports, and running services across the target network range — building a complete map of the organisation's network attack surface.

**What it scans:**
- Live host discovery and subnet enumeration
- Open TCP/UDP ports across all registered assets
- Service version detection via banner grabbing and fingerprinting
- Operating system detection and device classification
- Exposed management interfaces (RDP, SSH, Telnet, SNMP, etc.)
- Firewall and filtering rule inference
- Detection of rogue or unregistered devices on the network

**Tools & Tech:** `Nmap`, `Masscan`, `Netdiscover`

---

### 🌐 Web Scans

**What it does:** Automatically crawls and tests web applications and APIs for common vulnerabilities aligned with the OWASP Top 10, giving SMEs visibility into the security of their public-facing and internal web services.

**What it scans:**
- SQL Injection (SQLi) and NoSQL Injection
- Cross-Site Scripting (XSS) — Reflected, Stored, and DOM-based
- Broken authentication and session management weaknesses
- Security misconfigurations and exposed admin panels
- Sensitive data exposure (API keys, credentials, PII in responses)
- Outdated or vulnerable JavaScript libraries and third-party components
- SSL/TLS certificate validity, cipher strength, and protocol weaknesses
- HTTP security headers analysis (CSP, HSTS, X-Frame-Options, etc.)
- Directory traversal and path enumeration

**Tools & Tech:** `OWASP ZAP`, `Nikto`, `WhatWeb`, `SSLyze`, `testssl.sh`

---

### 🛢️ Database Scans

**What it does:** Audits database instances for security misconfigurations, excessive privileges, known vulnerabilities, and exposure risks — protecting the most sensitive layer of an SME's infrastructure.

**What it scans:**
- Unauthenticated or publicly accessible database ports (MySQL 3306, PostgreSQL 5432, MongoDB 27017, MSSQL 1433, etc.)
- Default or weak database credentials
- Excessive user privileges and improper role assignments
- Unencrypted database connections (missing TLS/SSL)
- Known CVEs in detected database engine versions
- Presence of sensitive data in publicly readable tables or collections
- Exposed backup files and database dumps on the filesystem or web

**Tools & Tech:** `Nmap` (DB NSE scripts), `sqlmap`, `Metasploit` auxiliary modules, custom Python DB auditor

---

### ⚙️ Configuration File Scans

**What it does:** Analyses system and application configuration files for hardening gaps, insecure defaults, and accidentally exposed secrets — a frequently overlooked but critical attack vector in SME environments.

**What it scans:**
- Hardcoded credentials, API keys, and tokens in config files
- Insecure file permissions on sensitive paths (`.env`, `web.config`, `/etc/passwd`, etc.)
- Misconfigured web server settings (Apache, Nginx, IIS)
- Exposed `.env`, `.git`, `config.yaml`, `settings.py`, and similar sensitive files
- SSH daemon configuration weaknesses (`PermitRootLogin`, `PasswordAuthentication`, etc.)
- Firewall and iptables rule analysis
- CIS Benchmark and system hardening compliance checks

**Tools & Tech:** `Lynis`, `TruffleHog`, `GitLeaks`, `Checkov`, custom grep-based secret scanner

---

## 🛠️ Tools & Technology

| Category | Tool / Technology | Purpose |
|---|---|---|
| **Language** | Python 3.10+ | Core orchestration, scripting, and automation |
| **Network Scanning** | Nmap, Masscan, Netdiscover | Host discovery, port scanning, service fingerprinting |
| **Web Scanning** | OWASP ZAP, Nikto, WhatWeb | OWASP Top 10 testing and web technology fingerprinting |
| **SSL/TLS Analysis** | SSLyze, testssl.sh | Certificate validity and cipher suite auditing |
| **Database Auditing** | sqlmap, Nmap NSE DB scripts, Metasploit aux | DB exposure, default credentials, and CVE checks |
| **Secret & Config Scanning** | TruffleHog, GitLeaks, Checkov, Lynis | Hardcoded secrets, misconfigured files, hardening benchmarks |
| **Asset Management** | SQLite / PostgreSQL, SQLAlchemy | Asset inventory, tagging, grouping, and scheduling |
| **Dashboard & UI** | Flask / Streamlit, Chart.js | Web-based results viewer and security posture dashboard |
| **Reporting** | Jinja2, WeasyPrint, ReportLab | PDF / HTML / JSON / CSV report generation |
| **Containerisation** | Docker, Docker Compose | Isolated, reproducible, and portable deployment |
| **Scheduling** | APScheduler, Cron | Automated recurring scan execution |

---

## 🚧 Further Work (In Progress)

The platform is actively being developed. The following features and improvements are currently in progress or planned for future releases:

- [ ]  **Full Web Dashboard** — Complete browser-based UI with scan scheduling, asset management, and live results
- [ ]  **Alert & Notification System** — Email/Slack alerts triggered when critical vulnerabilities are discovered
- [ ]  **Cloud Asset Discovery** — Integration with AWS, Azure, and GCP APIs to scan cloud-hosted resources
- [ ]  **CI/CD Pipeline Integration** — Plugin support for GitHub Actions and GitLab CI for DevSecOps workflows

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:2c5364,50:203a43,100:0f2027&height=100&section=footer" width="100%"/>

</div>
