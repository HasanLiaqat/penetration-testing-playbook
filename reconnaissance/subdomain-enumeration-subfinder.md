# Subdomain Enumeration with Subfinder

## Objective
Identify subdomains associated with a target domain to expand the attack surface during reconnaissance.

---

## What is Subdomain Enumeration?

Subdomain enumeration is the process of discovering subdomains belonging to a target domain.

Organizations often deploy different services on subdomains such as:

- api.example.com
- dev.example.com
- admin.example.com
- staging.example.com

These environments may contain misconfigurations or vulnerabilities.

---

## Tool

Subfinder – a fast passive subdomain enumeration tool developed by ProjectDiscovery.

Subfinder collects subdomains from various public sources like certificate transparency logs, DNS data, and APIs.

---

## Installation

### Kali Linux

Install using:

```
sudo apt install subfinder
```

Or using Go:

```
go install -v github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
```

---

## Basic Usage

```
subfinder -d example.com
```

Explanation:

| Flag | Meaning |
|-----|--------|
| -d | Target domain |

---

## Save Output to File

```
subfinder -d example.com -o subdomains.txt
```

This stores discovered subdomains in a file for further analysis.

---

## Example Output

```
api.example.com
dev.example.com
mail.example.com
staging.example.com
admin.example.com
```

Each discovered subdomain may host a different application or service.

---

## Next Steps After Discovery

After identifying subdomains, testers typically:

1. Check if the subdomain is live
2. Scan for open ports
3. Perform directory discovery
4. Test for vulnerabilities

---

## Risk Impact

Unmonitored subdomains can expose:

- development environments
- debug panels
- outdated applications
- misconfigured services

Attackers often target these overlooked systems.

---

## Mitigation & Defense

Organizations should:

- maintain an inventory of all subdomains
- remove unused subdomains
- restrict access to development environments
- regularly perform security assessments

---

## Reflection

Subdomain enumeration is a critical reconnaissance step that helps identify additional attack surfaces and hidden infrastructure.
