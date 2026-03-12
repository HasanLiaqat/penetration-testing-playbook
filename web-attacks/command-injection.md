# Command Injection Vulnerabilities

## Objective
Understand how improper input validation can allow attackers to execute system commands on a web server.

---

## What is Command Injection?

Command injection occurs when a web application passes user input directly to system commands without proper sanitization.

Attackers can manipulate inputs to execute arbitrary commands on the server.

Example:

```
ping [user_input]
```

If the application directly uses user input in a shell command, attackers can execute commands like:

```
; ls -la
```

---

## Common Attack Scenario

Many web applications take user input for:

- Ping/traceroute tools
- File manipulation scripts
- System status commands

If input is not sanitized, an attacker may run:

```
; whoami
; cat /etc/passwd
```

---

## Example Lab Testing

1. Identify vulnerable input fields
2. Test with simple payload:

```
127.0.0.1; id
```

3. Observe if the command executes and returns system info

---

## Realistic Exploit Example

- Input:

```
127.0.0.1; ls /var/www/html
```

- Result: attacker can see server files
- Risk: escalate to file upload or web shell exploitation

---

## Mitigation & Defense

To prevent command injection:

- Avoid passing user input directly to system commands
- Use proper input validation and sanitization
- Use language-specific safe functions (e.g., Python `subprocess.run` with lists)
- Apply the principle of least privilege for web application users
- Monitor server logs for suspicious input

---

## Risk Impact

Exploitable command injection can lead to:

- Full server compromise
- Sensitive data theft
- Pivoting to internal networks
- Installing persistent backdoors

Risk Level: Critical

---

## Reflection

Command injection is one of the most dangerous web vulnerabilities.  
It highlights the importance of **never trusting user input** and using secure coding practices.
