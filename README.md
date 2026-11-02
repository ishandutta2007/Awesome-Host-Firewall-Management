# Awesome-Host-Firewall-Management

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)

> A curated list of leading SaaS platforms, enterprise Network Security Policy Management (NSPM) suites, and open-source host firewall management projects. Focuses on endpoint firewall policies, workload microsegmentation, and self-hosted host-based network security controls.

**Last updated: November 2026**

---

## Table of Contents

- [Sector Overview & Market Dynamics](#sector-overview--market-dynamics)
- [SaaS & Enterprise Firewall Management Platforms](#saas--enterprise-firewall-management-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

---

## Sector Overview & Market Dynamics

The global Network Security Policy Management (NSPM) and Firewall Management market is valued at approximately **$7.7 billion to $9.0 billion in 2025–2026** (with core dedicated NSPM orchestration software accounting for roughly **$2.96B to $3.24B**, expanding at a 7–9% CAGR, and broader cloud/enterprise firewall management reaching upwards of $10B+). The market structure is **moderately fragmented at the application and host-level enforcement tier**, yet **highly concentrated among a few dominant category leaders** (such as Microsoft, Broadcom/Symantec, and CrowdStrike in endpoint security, and Tufin, AlgoSec, and FireMon in multi-vendor enterprise policy orchestration). Enterprise adoption is heavily driven by Zero Trust microsegmentation mandates, hybrid multi-cloud complexities, and automated continuous compliance frameworks (NIST, PCI-DSS, DORA).

---

## SaaS & Enterprise Firewall Management Platforms

The following table compares leading SaaS and commercial host firewall policy orchestration platforms, ordered by company scale (market cap / corporate valuation, descending):

| Product | Company | Company Size (Valuation / Revenue) | Pricing | Free Tier / Trial Limit | Key Focus & Capabilities |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **[Microsoft Defender Firewall](https://www.microsoft.com/en-us/security/business/microsoft-defender)** | Microsoft | **$3.85T Market Cap** (~$260B+ Rev) | From **$3.00/user/month** (Defender for Business standalone; covers up to 5 devices/user) or bundled in M365 Business Premium / E3 | **30-Day Free Trial** (up to 300 users in SMB trial; 90-day evaluation for enterprise M365 E3/E5 tiers) | Centralized Windows/macOS firewall rule management via Intune & Defender portal; profiles for Domain, Private, and Public networks. |
| **[Symantec Endpoint Protection Firewall](https://www.broadcom.com/)** | Broadcom | **$1.60T Market Cap** (~$64B+ Rev) | From **~$16.00 – $20.00/device/year** (entry-tier volume reseller packs; custom enterprise licensing) | **30 to 60-Day Trial** (available via Broadcom enterprise sales & partner evaluation tenants) | Host-based stateful packet filtering, stealth browsing settings, automatic attacker IP banning, and intrusion prevention. |
| **[CrowdStrike Falcon Firewall Management](https://www.crowdstrike.com/)** | CrowdStrike | **$260B Market Cap** (~$4.8B Rev) | From **$99.99/device/year** ($14.99/device billed monthly under Falcon Pro tier) | **15-Day Free Trial** (full core platform access with Falcon sensor) and **30-Day Test Drive** (sandboxed lab) | Native host firewall policy orchestration integrated with Falcon agent; granular inbound/outbound rules and network location profiles. |
| **[Check Point Quantum](https://www.checkpoint.com/)** | Check Point Software | **$15.5B Market Cap** (~$2.6B Rev) | Hardware appliances from **~$500** (Spark) to **$26,000+** (Quantum Force NGFW); Endpoint SaaS from **$22/user/year** ($1,100/yr for 50-seat pack) | **30-Day Free Trial** (available for Harmony Endpoint SaaS and Quantum virtual gateway/SD-WAN modules) | Enterprise next-generation firewall gateways, R82 HyperFlow acceleration, VSX virtual gateways, and unified endpoint security. |
| **[Sophos Firewall](https://www.sophos.com/)** | Sophos (Thoma Bravo) | **$3.9B Acquisition** (~$1.0B Rev) | Hardware appliances from **~$500 – $900** (XGS series); Endpoint protection from **~$35 – $70/user/year** | **30-Day Free Trial** (via Sophos Central cloud platform, soft-capped at 1,000 items per object type) | Coordinated host and network firewall security; Intercept X integrates endpoint network isolation with central Xstream firewall policies. |
| **[Illumio Core](https://www.illumio.com/)** | Illumio | **$2.75B Valuation** (~$150M+ Rev) | From **~$30 – $80/workload/year** (volume-tiered; baseline starting packs from ~$25,000 – $38,000/year) | **14 to 30-Day Free Trial** (Illumio Insights sandboxed trial with read-only cloud flow logs; multi-cloud telemetry) | Zero Trust host microsegmentation; deploys Virtual Enforcement Nodes (VEN) to enforce workload-level policies and dependency maps. |
| **[Trellix Host IPS](https://www.trellix.com/)** | Trellix (STG) | **~$2.0B Valuation** (~$1.5B Rev) | From **~$73.00 – $75.00/node/year** (Endpoint Essentials Cloud baseline; multi-tier enterprise quotes) | **60-Day Evaluation License** (capped at 5 nodes for on-prem ENS; up to 50 nodes for ePO-SaaS cloud trial) | Single-agent host intrusion prevention and firewall; Adaptive Mode auto-learns legitimate application network traffic. |
| **[Tufin Orchestration Suite](https://www.tufin.com/)** | Tufin (Turn/River Capital) | **$570M Acquisition** (~$110M Rev) | From **Free software AMI tier** on AWS (pay only EC2 compute); Enterprise TOS subscriptions from **~$10,000+/year** | **30-Day Free Trial** (app marketplace extensions & customized guided proof-of-concept for SecureTrack/SecureChange) | Multi-vendor network security policy management; normalizes rules across hybrid networks, cloud security groups, and perimeter firewalls. |
| **[AlgoSec](https://www.algosec.com/)** | AlgoSec | **~$200M Valuation** (~$80M+ Rev) | From **~$5,000/year** (baseline platform license for initial firewall cluster; scales per physical/virtual device) | **14 to 30-Day Guided PoC** (sales-assisted lab evaluation managing 5–10 test firewalls) | Application-centric security policy automation (Firewall Analyzer, FireFlow, AppViz); zero-touch automated compliance auditing. |
| **[FireMon](https://www.firemon.com/)** | FireMon | **~$150M Valuation** (~$70M+ Rev) | Modular pricing starting at **several thousand dollars/year** (scaled by managed network objects and firewall devices) | **14 to 30-Day Guided PoC** (pre-scoped lab deployment with dedicated solutions engineering support) | Real-time policy visibility, risk scoring, automated rule cleanup, and Agentic AI-driven policy change recommendations. |

---

## Open-Source GitHub Projects

A selection of top open-source host firewall managers, endpoint packet filters, application firewalls, and microsegmentation utilities, ranked by GitHub stars (descending):

| Project | Stars | Language | Primary Scope | Description |
| :--- | :---: | :--- | :--- | :--- |
| **[OpenSnitch](https://github.com/evilsocket/opensnitch)** | [![GitHub stars](https://img.shields.io/github/stars/evilsocket/opensnitch?style=social&color=white)](https://github.com/evilsocket/opensnitch/stargazers) | Python / Go | Linux Application Firewall | Interactive host application firewall for Linux inspired by Little Snitch; prompts users on outgoing network connections and creates per-process filtering rules. |
| **[ufw-docker](https://github.com/chaifeng/ufw-docker)** | [![GitHub stars](https://img.shields.io/github/stars/chaifeng/ufw-docker?style=social&color=white)](https://github.com/chaifeng/ufw-docker/stargazers) | Shell | Docker Host Firewall Management | Resolves the critical security flaw where Docker bypasses host UFW firewall rules by directly modifying iptables forwarding tables. |
| **[Fort Firewall](https://github.com/tnodir/fort)** | [![GitHub stars](https://img.shields.io/github/stars/tnodir/fort?style=social&color=white)](https://github.com/tnodir/fort/stargazers) | C++ / C | Windows Host Firewall | Lightweight open-source Windows personal host firewall using Windows Filtering Platform (WFP); controls per-application outbound traffic, bandwidth limits, and speed curves. |
| **[FireHOL](https://github.com/firehol/firehol)** | [![GitHub stars](https://img.shields.io/github/stars/firehol/firehol?style=social&color=white)](https://github.com/firehol/firehol/stargazers) | Shell | Linux Host/Gateway Firewall | Human-readable declarative language for configuring robust Linux iptables and Netfilter firewalls with zero-complexity rulesets and IP blacklisting. |
| **[firewalld](https://github.com/firewalld/firewalld)** | [![GitHub stars](https://img.shields.io/github/stars/firewalld/firewalld?style=social&color=white)](https://github.com/firewalld/firewalld/stargazers) | Python | Linux System Firewall Daemon | Stateful zone-based Linux host firewall daemon with D-Bus IPC interface, runtime/permanent rule separation, and native nftables/iptables backend support. |
| **[whalewall](https://github.com/capnspacehook/whalewall)** | [![GitHub stars](https://img.shields.io/github/stars/capnspacehook/whalewall?style=social&color=white)](https://github.com/capnspacehook/whalewall/stargazers) | Go | Container Host Firewall | Automated firewall rule orchestrator for Docker containers using nftables; provides isolated inter-container network filtering without manual iptables hacks. |
| **[befw](https://github.com/wgnet/befw)** | [![GitHub stars](https://img.shields.io/github/stars/wgnet/befw)](https://github.com/wgnet/befw/stargazers) | Go | Dynamic Multi-Host Firewall | Dynamic host-based firewall driven by HashiCorp Consul service discovery; protects registered datacenter services automatically across Linux nodes. |
| **[firewalld-gateway](https://github.com/cylonchau/firewalld-gateway)** | [![GitHub stars](https://img.shields.io/github/stars/cylonchau/firewalld-gateway?style=social&color=white)](https://github.com/cylonchau/firewalld-gateway/stargazers) | Go | Fleet Firewall Orchestration | Central controller and REST API bridge for firewalld; enables declarative and imperative batch management of firewalld across thousands of Linux servers. |
| **[Gnftato](https://github.com/Fiftonb/Gnftato)** | [![GitHub stars](https://img.shields.io/github/stars/Fiftonb/Gnftato?style=social&color=white)](https://github.com/Fiftonb/Gnftato/stargazers) | Vue / Node.js | Multi-Server Web Panel | Web-based management console for multi-server Linux nftables via SSH; includes built-in DDoS defense presets, port whitelists, and safe SSH preservation. |
| **[ufWall](https://github.com/The-Robin-Hood/ufWall)** | [![GitHub stars](https://img.shields.io/github/stars/The-Robin-Hood/ufWall?style=social&color=white)](https://github.com/The-Robin-Hood/ufWall/stargazers) | Rust | Terminal UI (TUI) | Modern terminal UI for UFW (Uncomplicated Firewall); visually navigates IPv4/IPv6 tables and simplifies rule deletion without manual rule-number lookups. |
| **[nfty](https://github.com/adrian-griffin/nfty)** | [![GitHub stars](https://img.shields.io/github/stars/adrian-griffin/nfty?style=social&color=white)](https://github.com/adrian-griffin/nfty/stargazers) | Go | Linux Host Firewall Manager | Enterprise-grade safety manager for nftables featuring automated commit-confirm rollback timers (prevents lockout), TOML config diffing, and Docker coexistence. |

---

## How to Contribute

Contributions are welcome! To propose a new SaaS platform or open-source host firewall project:

1. Fork this repository.
2. Add your entry into `README.md` keeping alphabetical order or star-count sorting intact.
3. Ensure the project is actively maintained, includes accurate pricing/licensing terms, and provides documentation.
4. Submit a Pull Request with a clear description of the project.

---

## Disclaimer

- This repository is a community-curated educational and technical resource. It does not constitute formal procurement or security endorsement.
- Host firewall rules operate at the kernel or network stack level; misconfigurations can disconnect remote administrator sessions. When experimenting on production hosts, always employ rollback mechanisms (e.g., `nfty` commit-confirm or scheduled timer reboots).
- Star counts and commercial pricing metrics are gathered from vendor data sheets, marketplace listings, and public repositories as of November 2026.
