# Active Directory Basics for Pentesters

## Objective
Understand how Active Directory works and why it is a major target during penetration testing and red team engagements.

---

## What is Active Directory?

Active Directory (AD) is a directory service developed by Microsoft for managing users, computers, and resources in a network.

It is commonly used in enterprise environments.

---

## Key Components

### Domain
A domain is a logical group of users and computers.

Example:
```
company.local
```

---

### Domain Controller (DC)

A Domain Controller is a server that:

- authenticates users
- enforces security policies
- manages domain resources

---

### Users & Groups

- Users → individual accounts
- Groups → collections of users with shared permissions

Example:
- Domain Admins
- IT Support

---

### LDAP

Lightweight Directory Access Protocol is used to query and manage directory services.

---

### Kerberos

Kerberos is the authentication protocol used in Active Directory.

It uses tickets instead of sending passwords over the network.

---

## Why Attack Active Directory?

If an attacker compromises AD, they can:

- control all users
- access sensitive data
- manage systems across the network
- maintain persistence

This is often the **ultimate goal** in red team engagements.

---

## Common AD Attack Techniques

### 1. Password Spraying

Trying common passwords across many accounts.

---

### 2. Kerberoasting

Extracting service tickets and cracking them offline.

---

### 3. Pass-the-Hash

Using stolen password hashes instead of plaintext passwords.

---

### 4. Privilege Escalation

Gaining higher privileges within the domain.

---

## Enumeration Basics

Attackers start by gathering information:

- domain users
- groups
- computers
- shares

Tools used:

- BloodHound
- PowerView
- enum4linux

---

## Real Pentesting Scenario

1. Gain initial access (phishing or vulnerability)
2. Enumerate domain users and groups
3. Identify weak accounts or misconfigurations
4. Escalate privileges
5. Move laterally across systems
6. Target Domain Controller

---

## Risk Impact

If Active Directory is compromised:

- entire organization is at risk
- attackers gain full control
- sensitive data can be exfiltrated
- long-term persistence is possible

---

## Mitigation & Defense

To secure Active Directory:

- enforce strong passwords
- implement multi-factor authentication
- monitor authentication logs
- restrict admin privileges
- regularly audit AD configurations

---

## Reflection

Active Directory is the backbone of most enterprise networks. Understanding its structure and weaknesses is essential for both attackers and defenders.
