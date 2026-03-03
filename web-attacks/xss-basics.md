# Cross-Site Scripting (XSS) Basics

## Objective
Understand how Cross-Site Scripting (XSS) vulnerabilities occur and how to identify them in a controlled lab environment.

## Lab Environment
- DVWA (Low security level)
- Kali Linux
- Web Browser Developer Tools

---

## What is XSS?

Cross-Site Scripting (XSS) is a web vulnerability that allows attackers to inject malicious JavaScript into web pages viewed by other users.

It occurs when user input is not properly validated or escaped before being rendered in the browser.

---

## Types of XSS

### 1. Reflected XSS
Payload is reflected immediately in the response.

### 2. Stored XSS
Payload is stored on the server (e.g., database) and executed when users view the page.

### 3. DOM-Based XSS
Vulnerability exists in client-side JavaScript.

---

## Basic Test Payload

```html
<script>alert('XSS')</script>
