# Advanced Nmap Scanning with NSE Scripts

## Objective
Learn how to use Nmap NSE (Nmap Scripting Engine) to perform advanced enumeration and vulnerability detection.

---

## What is NSE?

NSE stands for **Nmap Scripting Engine**.

It allows users to run scripts that automate tasks such as:

- service enumeration
- vulnerability detection
- brute force testing
- information gathering

These scripts extend Nmap’s functionality beyond simple port scanning.

---

## Basic Nmap Scan

Example:

```
nmap -sV 192.168.1.10
```

Explanation:

| Flag | Meaning |
|-----|--------|
| -sV | Detect service versions |

This identifies services running on open ports.

---

## Running Default NSE Scripts

```
nmap -sC -sV 192.168.1.10
```

Explanation:

| Flag | Meaning |
|-----|--------|
| -sC | Run default NSE scripts |
| -sV | Service version detection |

This performs basic enumeration automatically.

---

## Running Specific Scripts

Example: HTTP enumeration

```
nmap --script http-enum 192.168.1.10
```

This script attempts to find common web directories.

---

## Vulnerability Scanning

```
nmap --script vuln 192.168.1.10
```

This runs vulnerability detection scripts against the target.

---

## Brute Force Example

```
nmap --script ftp-brute -p 21 192.168.1.10
```

This attempts to brute-force FTP login credentials.

---

## Script Categories

Common NSE categories include:

- auth
- brute
- discovery
- vuln
- safe
- intrusive

Each category serves different penetration testing purposes.

---

## Listing Available Scripts

Nmap scripts are stored in:

```
/usr/share/nmap/scripts/
```

List them using:

```
ls /usr/share/nmap/scripts
```

---

## Real Pentesting Scenario

During reconnaissance, testers may:

1. Scan the network for open ports
2. Identify services and versions
3. Run NSE scripts for deeper enumeration
4. Identify potential vulnerabilities

This helps prioritize targets for exploitation.

---

## Risk Impact

Attackers can use NSE scripts to quickly identify:

- misconfigured services
- weak authentication mechanisms
- outdated software
- vulnerable network services

---

## Mitigation & Defense

To reduce risks:

- regularly patch services
- disable unnecessary ports
- monitor network traffic
- restrict external access

---

## Reflection

NSE scripts significantly enhance Nmap’s capabilities and make it one of the most powerful reconnaissance tools used in penetration testing.
