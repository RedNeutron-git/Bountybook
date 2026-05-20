# 📖 Bountybook

> A structured penetration testing methodology reference for ethical hackers, bug bounty hunters, and security researchers.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Status](https://img.shields.io/badge/status-active-brightgreen.svg)
![Made with](https://img.shields.io/badge/made%20with-Markdown-lightgrey.svg)
![For](https://img.shields.io/badge/for-ethical%20hacking%20only-red.svg)

---

## 📌 What is Bountybook?

**Bountybook** is a practical, phase-by-phase penetration testing methodology guide designed for:

- 🔍 **Bug bounty hunters** looking for a structured workflow
- 🧑‍💻 **Junior pentesters** building their methodology from scratch
- 🛡️ **Security teams** standardizing their internal testing process
- 🎓 **Students** learning ethical hacking in lab environments

It covers everything from **pre-engagement** to **post-exploitation**, with real commands and tools used at each phase.

---

## 📂 Repository Structure

```
Bountybook/
│
├── README.md                          # You are here
└── pentest_methodology_xxxyyzz_EN.md  # Full pentest methodology (EN)
```

---

## 🗺️ Methodology Overview

The methodology follows a 6-phase approach based on industry standards (PTES, OWASP):

| Phase | Name | Description |
|-------|------|-------------|
| 1 | **Pre-Engagement** | Define scope, sign RoE, prepare environment |
| 2 | **Passive Reconnaissance** | OSINT, WHOIS, DNS, subdomain enumeration |
| 3 | **Active Reconnaissance** | Port scanning, directory brute force, visual recon |
| 4 | **Vulnerability Assessment** | Web scanning, SSL checks, parameter discovery |
| 5 | **Exploitation** | SQLi, XSS, SSRF, Auth bypass, File upload |
| 6 | **Post-Exploitation** | Privilege escalation, sensitive file access |

---

## 🛠️ Tools Referenced

| Category | Tools |
|----------|-------|
| OSINT & DNS | `whois`, `dig`, `subfinder`, `amass`, `crt.sh` |
| Web Fingerprinting | `whatweb`, `curl`, `waybackurls`, `gau` |
| Port Scanning | `nmap` |
| Directory Brute Force | `gobuster`, `ffuf`, `feroxbuster` |
| Visual Recon | `gowitness`, `eyewitness` |
| Web Scanning | `nikto`, `OWASP ZAP`, `sslyze`, `testssl.sh` |
| Parameter Discovery | `arjun`, `katana`, `hakrawler` |
| Exploitation | `sqlmap`, `dalfox`, `xsstrike`, `hydra`, `Burp Suite`, `ssrfmap` |
| Post-Exploitation | `linpeas`, manual enumeration |

---

## 🚀 Getting Started

### Prerequisites

Most tools can be installed on **Kali Linux** or any Debian-based distro:

```bash
# Update system
sudo apt update && sudo apt upgrade -y

# Install core tools
sudo apt install -y nmap gobuster nikto whois dnsutils curl hydra sqlmap

# Install Go-based tools
go install github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
go install github.com/projectdiscovery/amass/v3/...@latest
go install github.com/ffuf/ffuf/v2@latest
go install github.com/projectdiscovery/katana/cmd/katana@latest

# Install Python tools
pip install arjun xsstrike
```

### Recommended Setup

```bash
# Clone this repo
git clone https://github.com/yourusername/Bountybook.git
cd Bountybook

# Open the methodology guide
cat pentest_methodology_xxxyyzz_EN.md
```

---

## ⚡ Quick Workflow

```bash
# 1. Passive recon
subfinder -d target.com -o subdomains.txt
amass enum -passive -d target.com

# 2. Port scan
nmap -p- --min-rate 5000 -T4 target.com -oN ports.txt

# 3. Directory brute force
ffuf -w /usr/share/wordlists/dirb/common.txt -u https://target.com/FUZZ -mc 200,301,302

# 4. Vulnerability scan
nikto -h https://target.com -o nikto.txt

# 5. Parameter discovery
arjun -u https://target.com/page -oJ params.json
```

---

## 📋 Checklist Before You Start

- [ ] Written authorization / Rules of Engagement signed
- [ ] Scope clearly defined (domains, IPs, excluded systems)
- [ ] Testing window confirmed with the client
- [ ] Emergency contact available
- [ ] Note-taking tool ready (e.g., Obsidian, Notion, CherryTree)
- [ ] VPN / isolated environment configured

---

## 📝 Reporting

After testing, always produce a structured report:

```
1. Executive Summary        → For management (non-technical)
2. Scope & Methodology      → What was tested and how
3. Findings                 → Each vulnerability with:
   ├── Title & description
   ├── Risk level (Critical / High / Medium / Low / Info)
   ├── CVSS Score
   ├── Proof of Concept (screenshots, request/response)
   ├── Business impact
   └── Remediation recommendation
4. Conclusion               → Prioritized fix roadmap
5. Appendix                 → Raw tool output, activity logs
```

**Recommended reporting tools:** `Pwndoc` · `SysReptor` · `Dradis`

---

## 🎯 Recommended Practice Platforms

Build your skills legally on these platforms before testing real targets:

| Platform | Type | Link |
|----------|------|-------|
| HackTheBox | Labs & CTF | https://hackthebox.com |
| TryHackMe | Guided learning | https://tryhackme.com |
| PentesterLab | Web app focus | https://pentesterlab.com |
| VulnHub | Offline VMs | https://vulnhub.com |
| HackerOne | Bug bounty | https://hackerone.com |
| Bugcrowd | Bug bounty | https://bugcrowd.com |

---

## ⚠️ Legal Disclaimer

> This repository is intended **strictly for educational purposes** and **authorized security testing only**.
>
> - Never test systems without **explicit written permission**.
> - Unauthorized access to computer systems is **illegal** and punishable by law.
> - The author assumes **no responsibility** for misuse of any information or tools referenced here.
>
> Always hack ethically. Always hack legally.

---

## 🤝 Contributing

Contributions are welcome! If you'd like to add a new phase, tool, or technique:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/add-new-phase`)
3. Commit your changes (`git commit -m 'Add: new technique for XYZ'`)
4. Push to the branch (`git push origin feature/add-new-phase`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgements

- [OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)
- [PTES — Penetration Testing Execution Standard](http://www.pentest-standard.org/)
- [SecLists by danielmiessler](https://github.com/danielmiessler/SecLists)
- [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings)

---

<p align="center">Made with ❤️ for the ethical hacking community</p>
