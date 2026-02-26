# Nmap Enumeration

## Objective
Perform network scanning and service enumeration in a controlled lab environment to understand the target's attack surface.

## Tool
- **Nmap** – Network exploration and security auditing tool  
- **Lab Environment** – Metasploitable 2 running in VirtualBox

## Key Concepts
- **Port Scanning:** Identify open ports that may have vulnerable services  
- **TCP vs UDP scanning:** TCP is connection-oriented; UDP is connectionless  
- **Service Detection:** Determine which services are running and their versions  
- **Common Nmap Flags:**
  - `-sS` – SYN scan (stealthy)
  - `-sV` – Service version detection
  - `-O` – OS detection
  - `-p` – Specify port(s)
  - `-p-` – Scan all ports

## Example Commands

```bash
# Basic SYN scan
nmap -sS 192.168.56.101

# Service version detection
nmap -sV 192.168.56.101

# Scan all ports with OS detection
nmap -p- -O -sV 192.168.56.101
