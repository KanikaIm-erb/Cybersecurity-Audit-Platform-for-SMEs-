<div align="center">

<!-- Banner -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,50:203a43,100:2c5364&height=200&section=header&text=%20AutoSec%20Audit%20Platform&fontSize=36&fontColor=ffffff&fontAlignY=38&desc=Automated%20Security%20Audit%20Platform%20for%20SMEs&descAlignY=58&descColor=a8dadc" width="100%"/>

<br/>

![Status](https://img.shields.io/badge/Status-In%20Development-orange?style=for-the-badge&logo=github)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Security](https://img.shields.io/badge/Focus-Cybersecurity-red?style=for-the-badge&logo=shield&logoColor=white)

<br/>

> **Empowering Small & Medium Enterprises with enterprise-grade security auditing — automated, affordable, and actionable.**

</div>

---

## 📚 Table of Contents

- [📖 Overview](#-overview)
- [⚠️ Problem Statement](#️-problem-statement)
- [✨ Key Features](#-key-features)
  - [🔍 Network Scanning](#-network-scanning)
  - [🌐 Web Application Testing](#-web-application-testing)
  - [🔑 Authentication & Access Auditing](#-authentication--access-auditing)
  - [📋 Compliance Checks](#-compliance-checks)
  - [📊 Automated Reporting](#-automated-reporting)
- [🛠️ Tools & Technology](#️-tools--technology)
- [🚧 Further Work (In Progress)](#-further-work-in-progress)
- [📜 License](#-license)
- [🙏 Credits & Acknowledgements](#-credits--acknowledgements)

---

## 📖 Overview

The **Automated Security Audit Platform for SMEs** is an open-source, end-to-end security auditing solution designed specifically for Small and Medium-sized Enterprises (SMEs). It orchestrates a suite of industry-standard open-source tools to automatically scan, assess, and report on an organisation's security posture — with minimal manual effort required.

Unlike expensive enterprise security suites, this platform brings together the best free and open-source tools into a unified, easy-to-deploy pipeline — making robust cybersecurity accessible to organisations with limited IT resources and budgets.

---

## ⚠️ Problem Statement

> *Small and medium-sized enterprises account for over **43% of all cybercrime targets** globally, yet most lack the resources to conduct regular, comprehensive security audits.*

**The core challenges SMEs face:**

- 💸 **Cost** — Professional penetration testing and security audits can cost thousands per engagement
- 🧑‍💻 **Expertise Gap** — SMEs rarely employ dedicated security professionals
- ⏱️ **Time** — Manual audits are slow, inconsistent, and rarely repeated
- 📉 **Visibility** — Without continuous scanning, vulnerabilities go undetected for months
- 📄 **Reporting** — Raw tool outputs are complex and not actionable for non-technical stakeholders

This platform addresses all of the above by providing an **automated, repeatable, and report-ready** security audit pipeline tailored for the SME threat landscape.

---

## ✨ Key Features

### 🔍 Network Scanning

**What it does:** Discovers all live hosts, open ports, and running services across the target network or IP range.

**What it scans:**
- Live host discovery across subnets
- Open TCP/UDP ports
- Service version detection (banners, fingerprinting)
- OS detection and network topology mapping
- Detection of exposed management interfaces (RDP, SSH, Telnet, etc.)

**Tools Used:** `Nmap`, `Masscan`

---

### 🌐 Web Application Testing

**What it does:** Automatically crawls and tests web applications for common vulnerabilities as defined by the OWASP Top 10.

**What it scans:**
- SQL Injection (SQLi)
- Cross-Site Scripting (XSS)
- Broken authentication and session management
- Security misconfigurations
- Sensitive data exposure (API keys, credentials in source)
- Outdated or vulnerable JavaScript libraries
- SSL/TLS certificate validity and cipher weaknesses

**Tools Used:** `OWASP ZAP`, `Nikto`, `WhatWeb`, `SSLyze`

---

### 🔑 Authentication & Access Auditing

**What it does:** Tests for weak, default, or commonly used credentials across exposed services and web portals.

**What it scans:**
- Default credentials on routers, admin panels, and services
- Brute-force susceptibility on SSH, FTP, HTTP Basic Auth, and RDP
- Password policy enforcement gaps
- Exposed login pages without rate limiting or lockout

**Tools Used:** `Hydra`, `Medusa`, custom wordlists

---

### 📋 Compliance Checks

**What it does:** Benchmarks the target environment against widely recognised security frameworks and best-practice guidelines.

**What it scans:**
- CIS Benchmark controls for Linux/Windows systems
- GDPR-relevant data exposure risks
- Basic ISO 27001 control alignment
- Patch and update status of key services

**Tools Used:** `Lynis`, custom compliance scripts

---

### 📊 Automated Reporting

**What it does:** Compiles all scan findings into a clean, structured, and non-technical report — ready to present to management or IT teams.

**What it produces:**
- Executive summary with overall risk score
- Categorised findings (Critical / High / Medium / Low / Informational)
- Per-finding remediation recommendations
- Trend comparison if historical scans exist
- Export formats: **PDF**, **HTML**, **JSON**

**Tools Used:** `Jinja2` templating, `WeasyPrint` / `ReportLab`, custom Python reporting engine

---

## 🛠️ Tools & Technology

| Category | Tool / Technology | Purpose |
|---|---|---|
| **Language** | Python 3.10+ | Core orchestration and scripting |
| **Network Scanning** | Nmap, Masscan | Port & host discovery |
| **Web Testing** | OWASP ZAP, Nikto | OWASP Top 10 vulnerability scanning |
| **SSL Analysis** | SSLyze, testssl.sh | TLS/SSL configuration auditing |
| **Auth Testing** | Hydra, Medusa | Credential & brute-force testing |
| **Compliance** | Lynis | System hardening benchmarking |
| **Reporting** | Jinja2, WeasyPrint | PDF/HTML report generation |
| **Containerisation** | Docker, Docker Compose | Isolated, portable deployment |
| **Scheduling** | Cron / APScheduler | Automated recurring scans |
| **Dashboard** | Flask / Streamlit *(planned)* | Web-based results viewer |

---

## 🚧 Further Work (In Progress)

The platform is actively being developed. The following features and improvements are currently in progress or planned for future releases:

- [ ] 🖥️ **Web Dashboard** — A browser-based UI for viewing scan results, scheduling audits, and managing targets
- [ ] 📬 **Alert & Notification System** — Email/Slack notifications when critical vulnerabilities are discovered
- [ ] ☁️ **Cloud Asset Discovery** — Integration with AWS, Azure, and GCP APIs to scan cloud-hosted resources
- [ ] 🔄 **CI/CD Pipeline Integration** — Plugin support for GitHub Actions and GitLab CI to enable DevSecOps workflows
- [ ] 🤖 **AI-Powered Risk Prioritisation** — Use LLM-based analysis to contextualise findings and prioritise remediation
- [ ] 📦 **One-Click Deployment** — Simplified installer script and Docker-based setup for non-technical users
- [ ] 🌍 **Multi-Tenancy Support** — Allow MSSPs or IT consultants to manage audits for multiple clients from a single instance
- [ ] 🗂️ **Historical Scan Comparison** — Track security posture over time with delta reports between scans
- [ ] 🧪 **Unit & Integration Testing Suite** — Comprehensive test coverage for all scanning modules

---

## 📜 License

This project is licensed under the **MIT License**.

```
MIT License

Copyright (c) 2025 Automated Security Audit Platform Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
```

See the full [`LICENSE`](./LICENSE) file for details.

> ⚠️ **Disclaimer:** This tool is intended for authorised security testing only. Always obtain explicit written permission before scanning any system or network you do not own. Misuse of this tool may be illegal.

---

## 🙏 Credits & Acknowledgements

This platform is built on the shoulders of giants. Huge thanks to the open-source security community and the following projects:

| Project | Description |
|---|---|
| [**Nmap**](https://nmap.org/) | The world's most powerful network scanner |
| [**OWASP ZAP**](https://www.zaproxy.org/) | Leading open-source web application security scanner |
| [**Nikto**](https://github.com/sullo/nikto) | Web server vulnerability scanner |
| [**Hydra**](https://github.com/vanhauser-thc/thc-hydra) | Network login cracker for auth testing |
| [**Lynis**](https://cisofy.com/lynis/) | Security auditing tool for Unix/Linux systems |
| [**SSLyze**](https://github.com/nabla-c0d3/sslyze) | SSL/TLS configuration analyser |
| [**OWASP Foundation**](https://owasp.org/) | For the OWASP Top 10 and security guidelines |

---

<div align="center">

**Made with ❤️ for the SME community**

*Security should not be a luxury — it's a right.*

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:2c5364,50:203a43,100:0f2027&height=100&section=footer" width="100%"/>

</div>
