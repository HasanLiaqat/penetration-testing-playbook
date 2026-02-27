# Burp Suite Basics

## Objective
Understand how to intercept, analyze, and manipulate HTTP requests in a controlled lab environment.

## Tool
- Burp Suite (Community Edition)
- Lab Environment: DVWA running on Metasploitable 2

## Key Concepts

### 1. Proxy
Burp Suite acts as an intercepting proxy between the browser and the web server, allowing inspection and modification of HTTP traffic.

### 2. HTTP Request Structure
- Method (GET / POST)
- URL
- Headers
- Body (parameters, credentials, etc.)

### 3. HTTP Response Structure
- Status code (200, 302, 403, etc.)
- Headers
- Response body

### 4. Important Modules
- Proxy → Intercept and view requests
- Repeater → Modify and resend requests
- Intruder → Automate payload testing (basic in Community version)

## Practical Example (DVWA Login Interception)

1. Configure browser to use Burp proxy (127.0.0.1:8080)
2. Enable Intercept
3. Submit login form
4. Capture POST request
5. Send request to Repeater
6. Modify username/password parameters and resend

Example intercepted request:

POST /dvwa/login.php HTTP/1.1
Host: 192.168.56.101
Content-Type: application/x-www-form-urlencoded

username=admin&password=password&Login=Login

## Observations
- Login credentials are transmitted in POST body
- No rate limiting observed in low-security setting
- Application behavior changes based on response message

## Risk Impact
If authentication mechanisms are weak:
- Brute force attacks become possible
- Credential stuffing risks increase
- Unauthorized access may occur

## Mitigation & Defense
- Implement rate limiting
- Use account lockout policies
- Enforce strong password policies
- Use HTTPS encryption
- Apply proper server-side validation

## Reflection
Understanding how HTTP requests function is essential before attempting attacks such as SQL injection or authentication bypass. Burp Suite provides visibility into application behavior and attack surfaces.
