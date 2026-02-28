# SQL Injection Basics

## Objective
Understand how SQL Injection vulnerabilities occur and how to identify and test them in a controlled lab environment.

## Lab Environment
- DVWA (Low security level)
- Kali Linux
- Burp Suite (for request analysis)

---

## What is SQL Injection?

SQL Injection (SQLi) is a web vulnerability that allows an attacker to manipulate database queries by injecting malicious SQL code into user input fields.

It occurs when user input is not properly validated or sanitized before being included in SQL queries.

---

## Why It Happens

Example vulnerable query:

SELECT * FROM users WHERE username = '$username' AND password = '$password';

If input is not sanitized, an attacker can inject:

' OR '1'='1

Which modifies the query logic and may bypass authentication.

---

## Types of SQL Injection

- Error-Based SQLi
- Union-Based SQLi
- Boolean-Based Blind SQLi
- Time-Based Blind SQLi

---

## Practical Lab Test (DVWA)

### Step 1: Identify Input Field
Navigate to DVWA → SQL Injection section.

### Step 2: Test Basic Payload

' OR 1=1 --

If the application returns multiple user records, it may be vulnerable.

### Step 3: Union-Based Example

' UNION SELECT null, database() --

Used to extract database information.

---

## Observations

- Application did not properly sanitize user input.
- Database errors revealed internal structure (on low security).
- The vulnerability allowed data extraction.

---

## Risk Impact

- Unauthorized access to sensitive data
- Full database compromise
- Credential exposure
- Potential remote code execution (in some environments)

---

## Mitigation & Defense

- Use prepared statements (parameterized queries)
- Apply proper input validation
- Implement least privilege database accounts
- Hide detailed error messages
- Use Web Application Firewall (WAF)

---

## Reflection

SQL Injection demonstrates how improper input handling can compromise entire systems. Understanding both exploitation and mitigation is critical for secure application development and effective penetration testing.
