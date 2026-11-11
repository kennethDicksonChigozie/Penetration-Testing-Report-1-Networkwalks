<div align="center">

# 🤖 PENETRATION TESTING REPORT

**FOOTPRINTING & NETWORK SCANNING PHASES**
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
   <img src="https://img.shields.io/badge/Kali%20Linux-404040?style=flat-square&labelColor=C00000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/windows os-404040?style=flat-square&labelColor=C00000&logo=windows&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />  
  <img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <div align="center">
<img src="https://img.shields.io/badge/👨🏽‍💻Pentester: Dickson%20Kenneth%20Chigozie-C00000?style=flat-square" />
</p>

---

<div align="center">
W2-PM-FINAL | CYBERSECURITY |  NETWORKWALKS 
</p>
  
</div> 
<p align="left">
🚧 Project Overview 
</p>

</div> 
<p align="left">
  
| **Field** | **Detail** |
|---|---|
| **Pentester** | **Dickson Kenneth Chigozie** |
| **Program/Batch** | Networkwalks-B084 |
| **Date** | 11<sup>th</sup> November, 2026 |
| **Modules completed** | W2-PM1 (Multiple Kali Tools)<br>W2-PM5 (Zenmap Scanning) |
| **Client/Target** | 1. Networkwalks (secured written permission already)<br>2. My own local LAN Network |
| **Permission secured from client?** | Yes |
| **Phases covered** | **Phase 1:** Reconnaissance & Footprinting<br>**Phase 2:** Scanning & Network Discovery<br>|

---

# 🎯 1. Liability Disclaimer

The activities documented in this report were conducted strictly on systems and devices for which prior written authorization was obtained, or on personally owned hardware. The contents of this document are intended strictly for educational and research purposes. The instructor, author, and Networkwalks assume no liability for the misuse or misapplication of this knowledge; all subsequent actions taken by the reader are their sole responsibility. Unauthorized system access constitutes a criminal offense in most jurisdictions, regardless of whether data or systems are damaged, and can result in severe legal penalties, significant fines, career impact (employment termination), and a permanent criminal record. 
> ⚠️ **Note: Authorization must be Secured from Networkwalks before performing reconnaisance & footprinting**

---

# ☄️ 2. Introduction

As part of my Networkwalks internship program (week 2), this report provides a comprehensive analysis of the Footprinting/Reconnaissance phases targeting the networkwalks.com domain and subsequent scanning of the local network utilizing Zenmap. By leveraging a combination of Kali Linux tools and Zenmap, this assessment simulates how a malicious actor actively maps live network hosts. The methodology mirrors an attacker's lifecycle, transitioning from passive data gathering (W2-PM1) to active host discovery (W2-PM5).

### 💡 Footprinting

All footprinting commands were executed within a Kali Linux environment.

### 🔎 Scanning activities 

Were performed via Zenmap on a windows host (pc). 

### 📝 Methodology, analysis framework, and documentation
To ensure reproducibility and rigorous documentation, every technical step outlines the exact commands utilized, corresponding system output, verification screenshots, and a brief analytical note from the attackers point of view regarding the security implications of the exposed data.

---

# ⚒️ 3. Tools Used

Each tool used and its purpose can be found in the table below.

| Tool/commands | Purpose |
|---|---|
| Kali Linux           | Operating system deployed to conduct initial reconnaissance and information gathering.          |
| Windows OS           | Host Operating systems utilized for networking activities including network mapping via Zenmap. |
| WHOIS                | Queries or Finds domain registration details such as registration ownership, critical dates, and authoritative name servers.                                                                                              |
| whatweb              | Identifies and fingerprints web technologies, including servers, CMS - content management system, plugins, and IP.                                                                                                         |
| nslookup             | Performs DNS lookup to resolve target domain names to their respective IP address               |
| curl -I              | Fetches, analyses, and reads the HTTP response headers of the website.                          |
| wafw00f              | Probes the web application to detect the presence and type of Web Application Firewall (WAF) present.                                                                                                                 |
| dnsrecon             | Enumerate or discovers all DNS records (NS, MX, SPF, TXT, SRV).                                 |
| Zenmap (Nmap GUI)    | Scan the local subnet to find live hosts, active IP addresses, and MAC addresses.               |
| Windows CMD          | Local IP and MAC address identification via a command line interface.                           |

---

---


<div align="center">
🛡️Activities Performed 
</p>

</div> 
<p align="left">

---

# 4. Footprinting & Reconnaissance Attacks With Multiple Kali Tools 
  
## 4.1. Background
Reconnaissance (also called as footprinting) is the first step in any real attack or security test. Before 
touching a target, an attacker quietly collects as much public information about it as possible. This 
includes who owns the domain, its real IP address, the hosting provider, the web technologies it 
runs, its DNS and mail records, and whether a firewall is protecting it. All of this comes from 
information the target has already made public, so the target never even knows it is being studied. 
This is why recon is powerful and very hard to detect.

> ⚠️ **In this lab, the live website networkwalks.com was footprinted.**

## 💡4.2. Footprinting & Reconnaissance

I performed reconnaissance against the `networkwalks.com` domain using six Kali Linux commands: 

```text
WHOIS
WhatWeb
Nslookup
Curl 
Wafw00f 
DNSRecon
```
> ⚠️ **Note: Each tool was used to collect a different type of information about the target as seen in table 3 above.**

---

### 4.2.1. WHOIS
WHOIS was used to obtain publicly available domain registration information and identify the domain’s name servers. The results provided information about the domain registration and hosting infrastructure.
> **Command used: ```whois networkwalks.com```**

<img width="1917" height="917" alt="whois screenshot 1" src="https://github.com/user-attachments/assets/546f1f6d-7062-4665-8032-a4563877ec81" />

<img width="1906" height="912" alt="whois screenshot 2" src="https://github.com/user-attachments/assets/fee668b7-409c-4c4a-995e-dbaa89d0efa8" />

<img width="1917" height="917" alt="whois screenshot 3" src="https://github.com/user-attachments/assets/51c1ad8d-0bc9-4528-9ab2-58d6a1dd314b" />


> ⚠️ **Security relevance: Here the name servers point to HostGator, so an attacker instantly learns the hosting provider. Registration dates, and abuse contacts help with social engineering and planning.**

---

### 4.2.2. Whatweb
WhatWeb was used to identify and fingerprint technologies used by the website.
> **Command used: ```whatweb networkwalks.com```**

<img width="1916" height="912" alt="whatweb screenshot" src="https://github.com/user-attachments/assets/d799cd28-0bbc-48e2-84cc-47327598a9f4" />

> ⚠️ **Security relevance: whatweb exposes the exact software and versions (here Wordpress 7.1.4 and WP Download 
Manager 3.3.76). An attacker looks these versions up in vulnerability databases to find known 
exploits. It also leaks the server IP and an email address.**

---

### 4.2.3 Nslookup
Nslookup was used to resolve the targets domain name to its IP address. The provided result identified ```192.232.216.135.```
> **Command used: ```nslookup networkwalks.com; OR, $ nslookup -vc networkwalks.com 8.8.8.8```**```**

<img width="1917" height="916" alt="nslook new snap" src="https://github.com/user-attachments/assets/7e46597a-07be-4002-b309-e6bcc855e53c" />

> ⚠️ **Security relevance: nslookup turns a domain name into its real IP address (192.232.216.135). Knowing the IP lets an 
attacker scan the server directly, look up other sites on the same IP, and map the target's 
infrastructure.**

---

### 4.2.4 curl
Curl was used with the -I option to inspect the HTTP response headers. This provided additional information about the web application and exposed the WordPress REST API endpoint /wp-json/.
> **Command used: ```curl -I https://networkwalks.com```**

<img width="1917" height="917" alt="curl -I screenshots" src="https://github.com/user-attachments/assets/375e46ed-24eb-4e69-8bb4-fb57f41e441a" />

> ⚠️ **Security relevance: HTTP headers leak the web server, caching stack and hidden endpoints (here the WordPress 
REST API at /wp-json/). Attackers read headers to fingerprint the stack and find entry points 
without even loading the full page.**

---

### 4.2.5 Wafwoof 
wafwoof was used to determine whether a Web Application Firewall was protecting the website. The result identified ModSecurity (SpiderLabs) Web Application Firewall.
> **Command used: ```wafwoof networkwalks.com```**

<img width="1915" height="917" alt="wafwoof screenshots" src="https://github.com/user-attachments/assets/61f36246-ea62-4bac-8b9b-1d7728c5d41d" />

> ⚠️ **Security relevance: wafwoof tells an attacker if a firewall is watching. Here the site sits behind ModSecurity
(SpiderLabs). Knowing a WAF is present shapes the whole attack: naive attempts will be blocked 
or logged, so the attacker must adapt or try to bypass it.**

---

### 4.2.6 dnsrecon 
dnsrecon was used to enumerate DNS records. The results provided information relating to name servers, mail servers, SPF/TXT records, service records and DNS software information.
> **Command used: ```dnsrecon -d networkwalks.com```**

<img width="1917" height="921" alt="dnsrecon screenshots" src="https://github.com/user-attachments/assets/c6cff838-3ba1-436a-a673-9502e6067b96" />

> ⚠️ **Security relevance: dnsrecon maps the target's entire DNS footprint: mail servers, DNS software version (Bind 
9.16.23), SPF policy and cPanel service records. Each record is a potential foothold and helps an 
attacker understand the email and hosting setup.**

---

## 🔎 5. Network Scanning with Zenmap
## 5.1. Background
Zenmap is the official GUI version of Nmap which can be used on Windows PC. It is a security scanner 
software tool which is used by Cybersecurity professionals & Hackers. It is a multi-platform (Linux, Windows, 
Mac OS X, BSD, etc.) free and open source application which aims to make Nmap easy for beginners to use 
while providing advanced features for experienced Nmap users. Frequently used scans can be saved as 
profiles to make them easy to run repeatedly.

---

## 5.2. Introduction and Objectives
For this second activity, I used **Zenmap** to perform **network discovery on my local network**. This practical required me to:
``` text
a). Identify my local IP address and subnet
b). Discover live hosts
c). Identify their IP addresses
d). Identify their MAC addresses
e). Generate a network topology
```

---

## 5.2.1. Procedure
- The Windows `ipconfig` command was entered in my cmd prompt to identify my `local IP address` and `LAN subnet`.
- I then entered the **subnet** into **Zenmap** and selected **Ping Scan** to identify **active hosts**.

---

## 5.2.2 Example of Hosts Identified
```text
192.168.56.1
192.168.0.190
```
- The example results also included two MAC addresses.

**See images below**

<img width="1907" height="1011" alt="nmap scan" src="https://github.com/user-attachments/assets/9947c40d-c121-4acc-a69c-73da483b61c3" />

<img width="1905" height="1012" alt="nmap 192 168 56 1" src="https://github.com/user-attachments/assets/3111f335-7fb8-405d-94ba-68935a2d87ff" />

---

# 📑 6. Networkwalks Zenmap Quiz Results

<img width="1920" height="1080" alt="nmap result 1" src="https://github.com/user-attachments/assets/575db887-5cd4-4f6f-a244-22cfa98bfdb9" />

<img width="960" height="540" alt="zenmap result 2" src="https://github.com/user-attachments/assets/9435631c-34dd-4451-819f-ea9195980ba1" />

<img width="960" height="540" alt="zenmap result 3" src="https://github.com/user-attachments/assets/183b9002-4551-4951-a8c3-b3a2f22d7dae" />

---

# 🎯 7. Risk Analysis / Impact

Based on the information collected during the footprinting and network scanning activities, I identified the following potential risks.

| **\#** | **Risk / Finding**                           | **Evidence / Observation**                                  | **⚠️Potential Impact**                                                                                            | **Risk Level** |
|--------|----------------------------------------------|-------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|----------------|
| 1      | Web technology information exposed           | WhatWeb identified WordPress and WP Download Manager        | Attackers may use exposed technology/version information to identify software requiring further security review | 🟡**Medium**   |
| 2      | Server IP address identifiable               | Nslookup resolved the domain to `192.232.216.135`           | Provides information about the network location of the web service                                    | 🟢 **Low**      |
| 3      | HTTP technical information exposed           | Curl returned HTTP response headers and exposed `/wp-json/` | May assist technology fingerprinting and further enumeration                                              | 🟢 **Low**      |
| 4      | WAF technology identifiable                  | Wafw00f identified ModSecurity (SpiderLabs)        | Reveals information about the web application’s security architecture                                         | 🟢 **Low**     |
| 5      | DNS infrastructure information exposed       | DNSRecon identified DNS, mail and service-related records   | DNS information can help build a broader infrastructure profile                                           | 🟡 **Medium**   |
| 6      | Multiple live hosts visible on local network | Zenmap identified four live hosts in the example network    | Unknown or unauthorized devices may potentially be present on a network                               | 🟡 **Medium**   |

### Risk Rating Key

| Indicator | Severity |
|---|---|
|🔴| **Critical** |
|🟡| **Medium**   |
|🟢| **Low**      |

> ⚠️ **Note: The risks above are observations from the footprinting and scanning exercises, not confirmed vulnerabilities. The practical exercises primarily involved information gathering and host discovery. No exploitation or vulnerability validation was performed as part of these two modules.
Therefore, the presence of information such as a software version, IP address or DNS record does not by itself mean that the system is vulnerable. Further authorized security testing would be required to confirm any actual vulnerability.**

---

# 🛡️ 8. Recommendations

## Based on the observations from these activities, I recommend the following security improvements:

1.  **Review publicly exposed technology information**  
    Organizations should regularly review what information about their web technologies, CMS and plugins is publicly visible.

2.  **Keep software updated**  
    CMS platforms, plugins and other web technologies should be regularly updated and reviewed against current security advisories.

3.  **Review HTTP headers**  
    HTTP response headers should be reviewed to determine whether unnecessary technical information is being exposed.

4.  **Review DNS records regularly**  
    DNS records should be checked periodically to ensure that only required information and services are publicly exposed.

5.  **Properly configure and monitor the WAF**  
    Keep the WAF (ModSecurity) enabled and tuned, since it already blocks naive attacks.

6.  **Perform regular internal network discovery**  
    Organizations should periodically scan their own networks to identify active devices.

7.  **Investigate unknown devices**  
    Any unexpected device discovered during network scanning should be investigated and verified.

8.  **Maintain network documentation**  
    Network topology and device information should be documented and updated regularly.

9.  **Perform security testing with authorization**  
    All Reconnaissance and scanning should only be performed against systems and networks where appropriate authorization has been provided.

---

# 🎯 9. Security Assessment Summary

| **Category** | **Status**| 
|---|---|
| 🔎 Reconnaissance and Footprinting | ✔️ Completed     |
| 🌐 Network Discovery               | ✔️ Completed     |
| 👨🏽‍💻 Host Identification             | ✔️ Completed     |
| ⏳ Network Topology                | ✔️ Completed     |
| 💥 Exploitation                    | ⏳ Not Performed |

---

# 🔚 10. Conclusion

During Week 2 of my Cybersecurity & Ethical Hacking internship, I completed authorized educational labs covering footprinting, reconnaissance, and network scanning.

Using Kali Linux tools (such as ```WHOIS, whatweb, nslookup, wafwoof, dnsrecon, ```) and Zenmap, I gathered targeted domain information, analyzed network configurations, mapped topologies, and collected IP/MAC addresses.

This experience emphasized that robust reconnaissance is critical for identifying vulnerabilities early, while professional reporting ensures those risks are clearly explained and effectively mitigated.

---

## 📌 Project Information

| **Project Details** | **Information** |
|---|---|
| 1️⃣ **Program Name** | Cybersecurity Program at Networkwalks            |
| 2️⃣ **Week**         | 02                                               |
| 3️⃣ **Project:**     | Authorized Penetration Testing Report            |
| 4️⃣ **Repository:**  | GitHub                                           |

---

<div align="center">
  
# 👤 Author

</div>

<div align="center">
  
**Ukwueze Uchenna Collins**

**Cybersecurity Intern | Networkwalks | Batch B084**

LinkedIn: www.linkedin.com/in/uchenna-u-6b4377367

</div>

---
