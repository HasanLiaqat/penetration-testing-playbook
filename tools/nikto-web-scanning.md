# Web Server Scanning with Nikto

## Objective
Identify common web server vulnerabilities, outdated software, and dangerous configurations using Nikto.

---

## What is Nikto?

Nikto is an open-source web server vulnerability scanner used during penetration testing.

It performs comprehensive scans against web servers to identify:

- outdated server versions
- dangerous files and scripts
- default configurations
- insecure HTTP headers
- known vulnerabilities

Nikto is useful during the **initial web reconnaissance phase**.

---

## Tool

Nikto – Web Server Vulnerability Scanner

---

## Installation

### Kali Linux

Nikto usually comes pre-installed.

Check installation:

```
nikto -h
```

If not installed:

```
sudo apt update
sudo apt install nikto
```

---

## Basic Scan

```
nikto -h http://target.com
```

Explanation:

| Flag | Meaning |
|-----|--------|
| -h | Target host |

---

## Scan a Specific Port

```
nikto -h http://target.com -p 8080
```

This scans a web service running on a non-standard port.

---

## Save Scan Results

```
nikto -h http://target.com -o results.txt
```

Output will be saved to a file for documentation.

---

## Example Findings

Nikto may detect issues such as:

- outdated Apache or Nginx versions
- directory indexing enabled
- exposed backup files
- insecure HTTP methods enabled

Example:

```
+ Server: Apache/2.2.8
+ Directory indexing enabled
+ X-Powered-By header exposed
```

---

## Risk Impact

Misconfigured or outdated servers may allow attackers to:

- exploit known vulnerabilities
- access sensitive files
- gather useful reconnaissance information

---

## Mitigation & Defense

To secure web servers:

- keep server software updated
- disable unnecessary HTTP methods
- remove sensitive files from public directories
- disable directory listing
- configure secure HTTP headers

---

## Reflection

Nikto helps identify common web server misconfigurations and vulnerabilities quickly. It is useful for initial reconnaissance before deeper manual testing.
