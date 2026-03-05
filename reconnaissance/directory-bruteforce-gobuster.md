# Directory Bruteforcing with Gobuster

## Objective
Discover hidden directories and files on a web server to identify additional attack surfaces.

## Tool
- Gobuster
- Wordlist: common.txt or directory-list-2.3-medium.txt

---

## What is Directory Bruteforcing?

Directory brute forcing is the process of discovering hidden directories and files on a web server by sending requests using a wordlist.

Applications often leave administrative panels, backup files, or testing endpoints exposed.

---

## Basic Gobuster Syntax

gobuster dir -u http://target-ip -w wordlist.txt

Explanation:

- dir → directory enumeration mode
- -u → target URL
- -w → wordlist used for discovery

---

## Example Scan

gobuster dir -u http://192.168.56.101 -w /usr/share/wordlists/dirb/common.txt

Example Output:

/admin
/uploads
/config
/backup

These directories may contain sensitive information or administrative interfaces.

---

## Observations

Hidden directories may expose:

- admin panels
- backup files
- configuration data
- file upload endpoints

Each discovered path should be manually investigated.

---

## Risk Impact

If sensitive directories are exposed:

- Unauthorized admin access
- Sensitive data exposure
- Misconfiguration exploitation

---

## Mitigation & Defense

- Disable directory listing
- Remove unnecessary files from production
- Restrict access to administrative paths
- Implement proper authentication controls

---

## Reflection

Directory discovery expands the attack surface during reconnaissance and often reveals hidden functionality that may contain vulnerabilities.
