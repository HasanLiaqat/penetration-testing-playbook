# Directory Enumeration with Gobuster

## What is Gobuster?

Gobuster is a fast brute-force tool used by penetration testers to discover hidden directories and files on web servers.

Web applications often contain hidden endpoints that are not directly linked on the website. Gobuster helps uncover them using wordlists.

Common discoveries include:

- Admin panels
- Hidden APIs
- Backup files
- Development pages
- Test environments

Finding these endpoints is important because they may expose sensitive functionality.

---

## Installation

### Kali Linux

Gobuster usually comes pre-installed.

Check installation:

```
gobuster -h
```

If not installed:

```
sudo apt update
sudo apt install gobuster
```

---

## Basic Directory Scan

```
gobuster dir -u http://target.com -w /usr/share/wordlists/dirb/common.txt
```

### Flag Explanation

| Flag | Meaning |
|-----|--------|
| `dir` | Directory brute forcing mode |
| `-u` | Target URL |
| `-w` | Wordlist used for guessing directories |

---

## Example Output

```
/admin
/login
/uploads
/api
/backup
```

These directories may contain sensitive or restricted functionality.

---

## Scanning for File Extensions

Sometimes important files are hidden with specific extensions.

Example:

```
gobuster dir -u http://target.com -w wordlist.txt -x php,html,txt
```

This searches for:

```
admin.php
login.html
backup.txt
config.php
```

---

## Increasing Scan Speed

Gobuster allows multi-threading to speed up scanning.

Example:

```
gobuster dir -u http://target.com -w wordlist.txt -t 50
```

### Flag Explanation

| Flag | Meaning |
|-----|--------|
| `-t` | Number of concurrent threads |

Higher threads = faster scan, but may increase server load.

---

## Useful Wordlists

Common wordlists used in pentesting:

```
/usr/share/wordlists/dirb/common.txt
/usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
/usr/share/wordlists/dirbuster/directory-list-2.3-big.txt
```

---

## Real Pentesting Scenario

Developers often leave sensitive directories exposed:

```
/admin
/dev
/backup
/old
/test
/staging
```

These directories may contain:

- Configuration files
- Backup databases
- Admin login panels
- Debug pages

Directory enumeration helps discover these hidden attack surfaces.

---

## Best Practice

Always perform directory enumeration during web application testing to identify hidden functionality and potential entry points for attacks.
