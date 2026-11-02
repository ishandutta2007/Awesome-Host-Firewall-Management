# Awesome-Host-Firewall-Management

# Top Host Firewall Management Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Endpoint Firewall Policy, Microsegmentation & Self-Hosted Host-Based Controls*  
**Last updated: November 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Host Firewall Management**. These tools enable organizations to control network traffic at the endpoint and workload level—enforcing least-privilege connectivity, blocking lateral movement, and maintaining visibility into host-based network activity without relying solely on perimeter defenses.

**Examples** include CrowdStrike Falcon Firewall Management, Microsoft Defender Firewall, Illumio Core, Symantec Endpoint Protection Firewall, Sophos Firewall, Check Point Quantum, Trellix Host IPS, AlgoSec, Tufin, and FireMon (the category leaders).

**Open-source emphasis**: Host Firewall Management is a domain where open-source tooling is **genuinely capable at the Linux host level but fragmented for enterprise-wide policy orchestration**. The strongest active projects are **nfty** (a Go-based nftables manager with commit-confirm rollback, lockout prevention, and TOML configuration) and **ufWall** (a terminal UI for UFW that makes host firewall management less error-prone). **Befw** provides dynamic host-based firewall rules driven by Consul service discovery, and **Gnftato** offers a web panel for managing nftables across multiple servers via SSH. The critical caveat: **no open-source project matches the multi-vendor policy orchestration** of Tufin or FireMon—those platforms normalize and audit firewall rules across Cisco, Check Point, Palo Alto, Fortinet, and cloud-native firewalls from a single control plane . Open-source host firewall tools operate at the individual host or Linux fleet level; enterprise NSPM remains commercial territory.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-products)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[CrowdStrike Falcon Firewall Management](https://www.crowdstrike.com/)**  
  Host-based firewall policy management integrated into the Falcon platform; provides API-driven rule group creation, network location management, and event export for visibility into endpoint traffic decisions .

- **[Microsoft Defender Firewall](https://www.microsoft.com/en-us/security/business/microsoft-defender)**  
  Windows Firewall management through Defender for Business and Intune; supports custom rules per network profile (Domain, Private, Public) with up to 150 custom rules per policy, managed via the Defender portal or Intune .

- **[Illumio Core](https://www.illumio.com/)**  
  Zero Trust segmentation platform providing **host-based microsegmentation** across data centers and clouds; uses VEN agents (or C-VEN for Kubernetes) to enforce workload-level policies, with real-time application dependency mapping and vulnerability-based segmentation . **Best for organizations wanting workload-level segmentation** rather than traditional firewall rule management.

- **[Symantec Endpoint Protection Firewall](https://www.broadcom.com/)**  
  Host-based firewall within Symantec Endpoint Protection; provides built-in rules for DHCP/DNS/WINS, traffic and stealth web browsing settings, attack detection and blocking (auto-blocking attacker IPs), and inbound traffic controls triggered by screensaver activation or firewall shutdown .

- **[Sophos Firewall](https://www.sophos.com/)**  
  While Sophos is primarily known for network firewalls (XGS Series), its endpoint protection includes host firewall capabilities integrated with Intercept X for endpoint-level traffic control.

- **[Check Point Quantum](https://www.checkpoint.com/)**  
  Enterprise security gateway with firewall capabilities; R82 release adds HyperFlow acceleration for SMB/CIFS and QUIC protocols, new troubleshooting tools (`connview`, `fw up_execute`), and enhanced VSX management for virtual gateways .

- **[Trellix Host IPS](https://www.trellix.com/)**  
  Host Intrusion Prevention with integrated firewall; provides stateful packet filtering and inspection, rule groups, trusted networks, and **Adaptive mode** that automatically creates allow rules for legitimate traffic to reduce false positives . **Best for organizations wanting combined HIPS + host firewall** from a single agent.

- **[AlgoSec](https://www.algosec.com/)**  
  Security policy management suite with Firewall Analyzer (network model and risk analysis), FireFlow (change automation), and AppViz (application-centric policy management); automates change workflows with zero-touch provisioning and continuous compliance .

- **[Tufin](https://www.tufin.com/)**  
  Network security policy management platform providing **unified visibility across hybrid mesh firewalls** (legacy, next-gen, cloud-managed); automates rule lifecycle management, network access orchestration, and continuous compliance validation against NIST, PCI DSS, and DORA . **Best for enterprises managing complex multi-vendor firewall estates**.

- **[FireMon](https://www.firemon.com/)**  
  Network security policy management with **Agentic AI** capabilities (October 2026); agents investigate access requirements, prepare policy change recommendations, and pause for practitioner review before any change is saved—nothing deploys automatically . Provides centralized policy visibility, risk scoring, and automated rule cleanup across Palo Alto, Cisco, Fortinet, Check Point, AWS, and Azure .

## Open-Source GitHub Projects

### Linux Host Firewall Managers (nftables, UFW)

- **[nfty](https://github.com/adrian-griffin/nfty)**  
  A **Go-based nftables manager for Linux** with enterprise-grade safety features. **Key differentiator**: **commit-confirm rollback**—every ruleset application starts a rollback timer (default 120s), stopped only when the user confirms with `nfty confirm`; if you lock yourself out or break a service, changes revert automatically . Also provides **TOML configuration** with diffing before apply, **lockout prevention** (detects SSH connections and warns about open sockets), **packet counters**, and **Docker compatibility** . Scoped to its own nftables table—does not touch Docker or other user tables, but snapshots all config for restoration . **Best for homelabs and Linux servers** wanting safe, reversible firewall changes—requires nftables and systemd.

- **[ufWall](https://github.com/The-Robin-Hood/ufWall)**  
  A **terminal UI for UFW** (Uncomplicated Firewall) that makes rule management visual and less error-prone. Features: firewall stats (on/off, outgoing policy, total rules), IPv4 and IPv6 rule tables with source/destination/port columns, and keyboard navigation . **Best for Linux users who find `ufw status numbered` and `ufw delete 7` anxiety-inducing**—but it is a UI wrapper, not a policy engine.

### Multi-Server & Dynamic Firewall Management

- **[Gnftato](https://github.com/Fiftonb/Gnftato)**  
  A **web-based multi-server nftables management panel** (Node.js/Vue.js) . Manages firewall rules across multiple servers via **SSH remote control**; features inbound/outbound control, port whitelisting, **DDoS defense rules**, and real-time status monitoring . **Safety defaults**: initialization and "clear all rules" preserve SSH, 80/tcp, and 443/tcp—SSH cannot be disabled via the panel . Docker-aware (preserves Docker NAT rules) . **Best for managing nftables across a fleet of Linux servers**—but it is a newer project requiring careful testing.

- **[befw](https://github.com/wgnet/befw)**  
  A **dynamic host-based firewall** (Go) using **Consul service discovery** to maintain rules across datacenters. Approach: if a service exists, protect it; if a client exists, allow it—using Consul catalog for services and KV storage for clients . Requires Consul cluster with ACL support on every node; provides `befw-cli`, `befw-firewalld`, and `befw-sync` components . **Best for organizations already using Consul** wanting service-discovery-driven firewall automation—but it is tightly coupled to Consul and PuppetDB for orchestration.

- **[firewalld-gateway (Uranus)](https://github.com/cylonchau/firewalld-gateway)**  
  A **Linux firewalld central controller** (Go) that converts firewalld's **full D-Bus API to REST API**, enabling management of thousands of Linux machines remotely . Features: declarative and imperative APIs, asynchronous batch operations, template switching for mass changes, and support for SQLite/MySQL . **Best for large Linux fleets** needing centralized firewalld management—but it requires opening D-Bus remotely (secured by IP restriction and ACL) .

### Additional Strong Open-Source Options

- **pfSense CE** — Open-source firewall distribution (FreeBSD) with web-based management; the most popular open-source network firewall, but it is a **network perimeter firewall**, not host-based management .
- **OPNsense** — Open-source firewall distribution (FreeBSD) with Suricata IPS inline mode and MVC/API firewall rule management; also perimeter-focused, not host-based .
- **IPFire** — Hardened Linux firewall distribution with Netfilter, firewall policy management, and rule cleanup; perimeter-focused .

**Frameworks for building custom systems**: For **safe Linux host firewall management with rollback**, nfty is the most safety-conscious open-source option . For **visual UFW management**, ufWall . For **multi-server nftables via web UI**, Gnftato . For **Consul-driven dynamic rules**, befw . For **centralized firewalld across thousands of hosts**, firewalld-gateway . **No open-source project matches the multi-vendor NSPM orchestration** of Tufin or FireMon—those normalize rules across Cisco, Check Point, Palo Alto, Fortinet, and cloud firewalls .

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Host firewall management tools handle network access controls on production systems; **misconfiguration can lock out administrators or break services**—nfty's commit-confirm rollback and lockout prevention are designed for exactly this risk, but should be tested in staging first . **Gnftato preserves SSH access by default**, but SSH cannot be disabled via the panel .
- **Open-source host firewall management is capable at the individual host and Linux fleet level but fragmented for enterprise NSPM**—nfty, ufWall, Gnftato, and befw address specific host-level needs . However, **no open-source project matches the multi-vendor policy orchestration** of Tufin or FireMon, which normalize and audit rules across heterogeneous firewall estates from a single control plane . Choose based on whether you need Linux host safety (nfty), multi-server management (Gnftato), or enterprise NSPM (commercial only).
- Verify license terms for commercial use; nfty and ufWall are open-source (check repositories), and Gnftato is open-source .

---

**Made for system administrators, security engineers, and platform teams managing host-level network controls.**  
Let's make host firewall management more open at the Linux host layer, but with clear eyes about the multi-vendor orchestration and enterprise audit gaps that commercial NSPM platforms still fill.
