---
layout: default
title: "Home"
---

# 👋 Hi, I'm Zain Shabaan

## Contact

- **GitHub:** [@zains786](https://github.com/zain786-cybersecurity/Projects)
- **LinkedIn:** **[zains786](https://www.linkedin.com/in/zains786)**
- **Email:** [zainshabaan@outlook.com](mailto:zainshabaan@outlook.com)
- **YouTube:** [@EverythingCyber786](https://www.youtube.com/@EverythingCyber786)



**Aspiring Cybersecurity Professional** focused on:

- Python security tools (encryption, phishing detection, network scanning)
- Building realistic home labs (Windows, Kali, Splunk, T-Pot, SIEM)
- Security awareness training (GoPhish simulations, posters, interactive games)

I learn by **doing** – building tools, running experiments in isolated labs, and then turning them into clear stories that non-technical people can understand.

---

##  How I Work & Learn

- I design labs that are **safe, isolated, and repeatable**.
- I write detailed LinkedIn posts to explain:
  - What I built
  - Why it matters
  - What I learned / would improve next time
- I’m actively growing towards roles like **SOC Analyst**, **Blue Team**, or **Junior Security Engineer**.

---

##  Quick Overview

- [Secure Password Manager (Python)](#secure-password-manager-python)
- [Phishing Email Detector (Python)](#phishing-email-detector-python)
- [Network Scanner (Python)](#network-scanner-python)
- [Cybersecurity Home Lab](#cybersecurity-home-lab)
- [DFIR & SIEM Lab with Splunk](#dfir--siem-lab-with-splunk)
- [T-Pot Honeypot on DigitalOcean](#t-pot-honeypot-on-digitalocean)
- [GoPhish Phishing Simulation](#gophish-phishing-simulation)
- [Complete Phishing Awareness System](#complete-phishing-awareness-system)
- [Wireshark Network Traffic Analysis (Kali Linux)](#wireshark-network-traffic-analysis-kali-linux)

---

##  Technical Skills

**Security & Platforms**

- Windows 10 endpoint hardening & logging (Defender, Sysmon)
- Kali Linux • VirtualBox • DigitalOcean droplets
- DFIR mindset, log analysis, basic threat hunting
- Honeypots (T-Pot, Cowrie, Dionaea) & attack surface monitoring

**Tools & Technologies**

- Python (CLI tools, automation, CSV/JSON processing)
- Splunk (searching, dashboards, endpoint index)
- ELK Stack basics (Elasticsearch, Logstash, Kibana via T-Pot)
- GoPhish for phishing simulations
- Networking basics (IP ranges, host-only networks, ports, services)

**Soft Skills**

- Clear written communication (LinkedIn write-ups, training content)
- Security awareness & education
- Experiment design, documentation, and reflection

---

##  PROJECTS – Security Tools

### Secure Password Manager (Python)

![Password Manager – master password flow](assets/images/project1-password-manager-terminal.png)
![Password Manager – Python code in VS Code](assets/images/project1-password-manager-code.png)

**Goal:** Build a real-world style **password manager** to practice secure authentication and encryption.

**What it does**

- Prompts the user to create a **master password**, stored only as a **salted, hashed value**.
- Uses **PBKDF2 (hashlib)** to derive a key and **Fernet (AES)** to encrypt stored passwords.
- Provides a simple **CLI menu**: add new passwords, view stored passwords (after correct master password).

**Key security concepts practiced**

- Master password authentication (salted + hashed)
- AES encryption for password storage
- Separating authentication, encryption, and storage concerns

**Tech stack**

> Python • `cryptography` (Fernet) • `hashlib` PBKDF2 • CLI design

---

### Phishing Email Detector (Python)

![Phishing detector – CLI report](assets/images/project2-phishing-detector-terminal.png)
![Phishing detector – JSON report](assets/images/project2-phishing-detector-json.png)
![Phishing detector – CSV summary](assets/images/project2-phishing-detector-csv.png)

**Goal:** Automatically analyse `.eml` files for phishing indicators and generate structured reports.

**What it does**

- Parses email headers and body content from `.eml` files.
- Checks for:
  - SPF/DKIM presence
  - Domain mismatches
  - Suspicious URLs & urgency phrases
  - Punycode/IP indicators
- Outputs both:
  - **JSON report** (per email)
  - **CSV report** summarising all scanned emails (timestamp, decision, flags, etc.)

**Why it matters**

This project simulates SOC-style triage: turning raw email data into **structured evidence** a defender could act on.

**Tech stack**

> Python • JSON & CSV reporting • email/header parsing • basic rule-based detection

---

### Network Scanner (Python)

![Network scanner – port scan function](assets/images/project3-network-scanner-code.png)
![Network scanner – CLI usage](assets/images/project3-network-scanner-terminal.png)
![Network scanner – CSV results](assets/images/project3-network-scanner-csv.png)

**Goal:** Build a fast, scriptable **network scanner** to discover open ports and services.

**What it does**

- Scans hosts and ports with **multithreading** for speed.
- Supports **CIDR notation & IP ranges** for flexible targeting.
- Identifies services like **SSH, HTTP, HTTPS** based on port.
- Writes results to **CSV** with: timestamp, host, port, service, open/closed, elapsed time.

**Key features**

- Threaded performance to handle many checks quickly.
- Custom timeout control to avoid long hangs.
- CSV logs suitable for later analysis or import into other tools.

**Tech stack**

> Python • `socket` • multithreading • CSV logging

---

## 🧪 PROJECTS – Labs & Environments

### Cybersecurity Home Lab

![VirtualBox lab – Windows + Kali VMs](assets/images/project4-homelab-vbox.png)
![VirtualBox host-only network config](assets/images/project4-homelab-network.png)
![Kali – IP config and ping tests](assets/images/project4-homelab-kali-ping.png)

**Goal:** Build a **safe, isolated environment** to run security experiments without risking real systems.

**What I built**

- VirtualBox home lab with:
  - **Windows 10 VM** (victim / endpoint)
  - **Kali Linux VM** (attacker)
- Configured a **Host-only network** so VMs can talk to each other but stay isolated from the internet.
- Assigned IP addresses and verified connectivity with **ICMP ping tests** between machines.

**Why it matters**

This lab is the base for many other projects: phishing simulations, network scans, malware testing, and DFIR exercises.

**Key tools**

> VirtualBox • Windows 10 • Kali Linux • Host-only networking

---

### DFIR & SIEM Lab with Splunk

![Kali attacker – host-only network view](assets/images/project5-dfir-kali.png)
![VirtualBox manager – DFIR lab VMs](assets/images/project5-dfir-vbox.png)
![Kali – Python HTTP server delivering payload](assets/images/project5-dfir-http-server.png)
![Windows Defender – real-time protection settings](assets/images/project5-dfir-defender.png)
![Kali – Nmap scan of Windows endpoint](assets/images/project5-dfir-nmap.png)
![Splunk – endpoint index search](assets/images/project5-dfir-splunk-endpoint.png)
![Splunk – event timeline view](assets/images/project5-dfir-splunk-timeline.png)

**Goal:** Build a **Digital Forensics & Incident Response** environment to understand how attacks are logged and detected.

**Lab components**

- VirtualBox environment with:
  - Windows 10 endpoint
  - Kali Linux attacker
  - Splunk SIEM instance
- Simulated payload delivery using a **Python HTTP server** hosting a fake `Resume.pdf.exe`.
- Generated activity on the Windows host (downloads, executions, network connections).

**What I practised**

- Secure virtualisation and host-only networking.
- Internal connectivity checks with **ICMP** and **Nmap**.
- Event logging & alert generation in **Windows Defender / Sysmon**.
- Log ingestion & analysis inside **Splunk**:
  - Searching by IP, time range, event IDs.
  - Correlating attacker IP activity to timeline events.

**Key tools**

> VirtualBox • Kali Linux • Windows 10 • Splunk • Sysmon • Nmap • Python HTTP server

---

### T-Pot Honeypot on DigitalOcean

![DigitalOcean droplet – T-Pot honeypot server](assets/images/project6-tpot-droplet.png)
![T-Pot installation script running](assets/images/project6-tpot-install.png)
![T-Pot – containers and services pulled](assets/images/project6-tpot-pulled.png)
![T-Pot web console – main dashboard](assets/images/project6-tpot-dashboard.png)
![T-Pot attack map – live global hits](assets/images/project6-tpot-attackmap.png)

**Goal:** Deploy a **cloud honeypot environment** and observe real attacker behaviour in the wild.

**What I built**

- Provisioned an **Ubuntu server droplet** on DigitalOcean.
- Installed the full **T-Pot honeypot platform**, including multiple honeypots (Cowrie, Dionaea, etc.) and the ELK stack.
- Reconfigured SSH and firewall rules as required by T-Pot.
- Accessed the **T-Pot web interface**, including:
  - Central dashboard
  - Attack Map with geolocation of sources
  - Tools like Kibana, CyberChef, Spiderfoot

**What I analysed**

- Live global attacks against the honeypot (login attempts, scans, exploitation traffic).
- Top source IPs, countries, ports, and services hit.
- Patterns in automated scanning and brute-force behaviour.

**Skills developed**

- Honeypot deployment & configuration
- Threat intelligence collection & basic analysis
- Cloud server management (billing, isolation, firewalling)
- Data visualisation and reporting with Kibana & dashboards

**Tech stack**

> DigitalOcean • Ubuntu Server • T-Pot • ELK Stack • Various honeypots

---

## 🧠 PROJECTS – Phishing & Awareness

### GoPhish Phishing Simulation

![GoPhish – spear-phishing email template](assets/images/project7-gophish-template.png)
![GoPhish – campaign results dashboard](assets/images/project7-gophish-results.png)

**Goal:** Understand how organisations run **phishing awareness campaigns** from the attacker and defender perspective.

**What I did**

- Deployed **GoPhish** inside my lab environment.
- Created a spear-phishing email template for a hospital IT verification scenario.
- Designed a matching **landing page** to capture test credentials.
- Configured sending profiles, user groups, and launched a test campaign.
- Reviewed the **campaign dashboard** (emails sent/opened, links clicked, data submitted, emails reported).

**What I learned**

- How attackers craft believable, high-pressure lures.
- How campaign metrics help security teams measure user behaviour.
- How GoPhish structures data for export and analysis.

**Tech stack**

> GoPhish • Kali Linux • HTML templates • Lab-only email simulation

---

### Complete Phishing Awareness System

![Interactive game – scenario choice screen](assets/images/project8-game-scenario.png)
![Interactive game – correct (unsafe) explanation](assets/images/project8-game-correct.png)
![Interactive game – incorrect explanation slide](assets/images/project8-game-incorrect.png)
![Pause and Verify – phishing awareness poster](assets/images/project8-poster.png)

**Goal:** Turn technical phishing experiments into a **holistic training experience** for non-technical staff.

This system combines three elements:

1. **Visual Awareness Poster**  
   - “**Pause and Verify**” design encouraging staff to stop and think before clicking email links.  
   - Simple, memorable messaging: *verify emails before clicking links*.

2. **Interactive Learning Game**  
   - Scenario: link to a hospital login page sent to a personal Gmail account.  
   - Users choose **SAFE** or **UNSAFE**, then receive instant feedback explaining:
     - How attackers impersonate hospital IT.
     - Why personal accounts are high-risk.
     - Why official portals and approved apps should always be used.

3. **GoPhish Simulation (from the previous project)**  
   - Connects the theory to realistic-looking phishing attempts.
   - Shows how user actions (clicks, submissions, reports) become data.

**Outcome**

By combining **simulation + design + education**, this project mirrors how real organisations train staff to recognise modern social-engineering attacks.

**Tech & tools**

> GoPhish • Presentation tools (interactive slides) • Poster design tools

---


## Wireshark Network Traffic Analysis (Kali Linux)

**Goal:** Use Wireshark in a Kali Linux virtual machine to capture and analyse real network traffic, focusing on HTTP, TCP streams and DNS lookups – building a stronger foundation in networking for cybersecurity.

**What I did**

- Ran Kali Linux in VirtualBox and captured live traffic on the active interface (`eth0`).
- Applied Wireshark display filters:
  - `http` – to inspect HTTP GET requests and `200 OK` responses.
  - `tcp` + **Follow ➝ TCP Stream** – to reconstruct full client–server conversations.
  - `dns` – to observe how domain names are resolved before web traffic is sent.
- Saved and documented three key views for analysis:
  - Raw HTTP request/response packets.
  - A full TCP stream showing the complete HTTP conversation.
  - DNS queries and responses for visited domains.

**What I learned**

- How browsers request pages using HTTP and how servers respond at the packet level.
- How multiple packets (with sequence and acknowledgement numbers) form a single TCP conversation.
- That DNS is the first step in most web traffic – resolving names like `example.com` to IP addresses.
- Why packet-level visibility is essential for incident response, troubleshooting and threat hunting.

**Screenshots**

![Wireshark HTTP capture – GET and 200 OK](assets/images/wireshark-http.jpg)
![Wireshark TCP stream – full HTTP conversation](assets/images/wireshark-tcp-stream.jpg)
![Wireshark DNS analysis – queries and responses](assets/images/wireshark-dns.jpg)


**Tech & tools**

> Kali Linux • Wireshark • VirtualBox • Basic networking (TCP/IP, HTTP, DNS)



##  PROJECTS – DevOps & Automation

###  CI Pipeline for Python Application
<div class="project-block">

**Goal:**  
Create a fully automated **Continuous Integration (CI)** pipeline using GitHub Actions to test and validate a Python application on every push or pull request.



**What it does**  
- Automatically triggers on commits to the `main` branch  
- Checks out the repository code  
- Sets up Python 3.10 in the CI runner  
- Installs dependencies from `requirements.txt`  
- Runs automated tests using `pytest`  
- Shows pass/fail results directly in the "Actions" tab  
- Ensures consistent quality and prevents broken code from being merged



**Why this matters**  
This pipeline mimics real DevOps workflows used in production teams, enforcing code quality, reliability, and automated testing. It demonstrates core CI/CD skills required for DevOps & DevSecOps roles.



**Tech Stack / Tools Used**  
> GitHub Actions • CI/CD • Python 3.10 • PyTest • YAML Workflows • Ubuntu Runner • Requirements Management

**Screenshots**

<p>
  <img src="/Projects/assets/images/devops-ci-1.png"
       alt="Wireshark HTTP capture – GET and 200 OK"
       style="max-width: 100%; border-radius: 12px; margin-bottom: 0.75rem;" />

  <img src="/Projects/assets/images/devops-ci-2.png"
       alt="Wireshark TCP stream – full HTTP conversation"
       style="max-width: 100%; border-radius: 12px; margin-bottom: 0.75rem;" />

  <img src="/Projects/assets/images/devops-ci-3.png"
       alt="Wireshark DNS analysis – queries and responses"
       style="max-width: 100%; border-radius: 12px; margin-bottom: 0.75rem;" />
</p>



---


If you’d like to talk about junior cybersecurity roles, projects, or collaborations, I’m always happy to connect.
