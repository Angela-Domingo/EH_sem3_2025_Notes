

## TCP and UDP Port Discovery

- Tool: `nmap -sS` for TCP, `nmap -sU` for UDP  
- Target: `scanme.nmap.org`  
- TCP vs UDP:  
  - TCP: Reliable, connection-based, three-way handshake  
  - UDP: Unreliable, connectionless, faster but no guarantee  
- Purpose: Identify running services via different transport protocols  

---

## Full Port Scan

- Tool: `nmap -p- testphp.vulnweb.com`  
- Purpose: Scan all 65,535 ports for hidden services  
- Why: Some services run on non-standard ports to avoid detection  

---

## DNS and IP Discovery

- Tool: `nmap -sL`, `dig zero.webappsecurity.com`  
- DNS: Converts domain names to IP addresses  
- Flowchart: Browser → DNS Resolver → Root → TLD → Authoritative → IP returned  

---

## Create Low-Privilege User

- Commands:  
  - `adduser student01`  
  - `deluser student01 sudo`  
- Why: Limits access; follows the principle of least privilege  

---

## File Creation and Permission

- Commands:  
  - `touch file.txt`  
  - `chmod 751 file.txt`  
  - `ls -l`  
- Permission 751:  
  - Owner: `rwx`  
  - Group: `r-x`  
  - Others: `--x`  

---

## What is Shodan?

- Site: [shodan.io](https://www.shodan.io)  
- Target: `scanme.nmap.org`  
- Findings: Exposed ports, services, metadata  
- Use:  
  - Attackers: Reconnaissance  
  - Defenders: Vulnerability assessment  

---

## Explain Core Network Terms

- NAT: Translates private IPs to public  
- ARP: Maps IP address to MAC  
- MAC: Physical address of a device  
- IPv4: 32-bit address, e.g. `192.168.1.1`  
- IPv6: 128-bit, more space, e.g. `2001:db8::1`  

---

## Directory Monitoring Bash Script

- Tool: `inotifywait` or `inotify-tools`  
- Monitors: `/home/student/Downloads`  
- Purpose: Logs create/delete/modify events for file security  

---

## Mini Port Scanner Script

- Script:  
  - Accepts IP input  
  - Scans top 1000 ports  
  - Saves results to `scan_<date>.log`  
- Purpose: Basic custom scanning tool  

---

## Linux AI Help Chat using Groq API

- Goal: CLI chatbot that explains Linux commands  
- Tech: Python + Groq API  
- Function: Input command → output explanation  

---

## Ncat Chat Terminal

- Command A: `ncat -l -p 1234`  
- Command B: `ncat <IP> 1234`  
- Purpose: Simple text chat between machines to demonstrate networking  

---

## Serve a Directory using Python

- Command: `python3 -m http.server 8080`  
- Purpose: Starts HTTP server to share files  
- Use: Learn how web servers serve content  

---

## VirusTotal API Usage

- Tool: `curl` + API key  
- Process:  
  - Upload hash  
  - Get JSON report  
- Why: Multi-engine malware check via file fingerprinting  

---

## Sudo Usage Logging

- Monitors: `/var/log/auth.log`  
- Checks: For `"sudo"` entries  
- Logs: Username and timestamp of sudo usage  

---

## System Hack Timeline

- Example: SolarWinds  
- Timeline:  
  1. Initial Access  
  2. Execution  
  3. Persistence  
  4. Privilege Escalation  
  5. Data Exfiltration  
  6. Detection & Response  

---

## Detect Service Version with Nmap

- Command: `nmap -sV testphp.vulnweb.com`  
- Findings: Software versions  
- Risk: Known versions may have CVEs (e.g., outdated Apache)  

---

## Bash Script for Auto Ping and Log

- Function: Ping a domain every 5 mins  
- Output: Logs response time to CSV  
- Purpose: Monitor network health & downtime  

---

## Discover Hidden Directories

- Tools: `dirb`, `gobuster`  
- Target: `testphp.vulnweb.com`  
- Goal: Discover directories like `/admin`, `/backup`, etc.  
- Why: May expose sensitive data  

---

## Python Socket Port Scanner

- Script: Python (≤15 lines)  
- Scans: Ports 1–100

# API (Application Programming Interface)

## What is an API?

An **API (Application Programming Interface)** is a set of rules that allows different software applications to communicate with each other. It defines how requests and responses should be made, what data formats to use, and how different components interact.

In simple terms, an API acts like a **messenger** that takes requests from one system, tells another system what to do, and returns the response.

Example: When you log in using Google on a third-party app, that app is using Google’s API to authenticate your credentials.

---

## Types of APIs

- **REST API** – Uses HTTP methods (GET, POST, PUT, DELETE), commonly used on the web.  
- **SOAP API** – Uses XML messages and is more structured.  
- **GraphQL** – Allows clients to request exactly the data they need.  
- **WebSocket API** – Enables real-time communication.  

---

## Uses of APIs

- **Integration**: Connect different systems or services (e.g., payment gateways, social logins).  
- **Communication**: Enable software components to talk to each other.  
- **Data Access**: Retrieve or send data from/to servers or databases (e.g., weather, news, stock APIs).  
- **Automation**: Trigger actions or workflows (e.g., sending emails, scheduling tasks).  
- **Microservices**: Connect and coordinate between independent services in distributed architectures.  

---

## Example Use Case

A weather app uses the OpenWeatherMap API to fetch current temperature data by sending an HTTP request like:

```http
GET https://api.openweathermap.org/data/2.5/weather?q=London&appid=YOUR_API_KEY
