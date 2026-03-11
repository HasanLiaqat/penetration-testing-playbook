# Password Cracking with John the Ripper

## Objective
Understand how penetration testers recover plaintext passwords from hashed values using password cracking tools.

---

## What is John the Ripper?

John the Ripper is a popular password cracking tool used by security professionals to test password strength.

It attempts to recover passwords from hashed values using techniques like:

- Dictionary attacks
- Brute force attacks
- Rule-based attacks

It is commonly used during penetration testing after obtaining password hashes from databases or system files.

---

## Installation

### Kali Linux

John the Ripper usually comes pre-installed.

Check installation:

```
john --help
```

If not installed:

```
sudo apt update
sudo apt install john
```

---

## Understanding Password Hashes

Systems do not store passwords in plain text.  
Instead, they store **hashes**.

Example MD5 hash:

```
5f4dcc3b5aa765d61d8327deb882cf99
```

This hash corresponds to the password:

```
password
```

Password cracking tools attempt to reverse hashes by testing many possible passwords.

---

## Dictionary Attack

Create a file containing hashes.

Example:

```
hashes.txt
```

Contents:

```
5f4dcc3b5aa765d61d8327deb882cf99
```

Run John the Ripper:

```
john --wordlist=/usr/share/wordlists/rockyou.txt hashes.txt
```

Explanation:

| Flag | Meaning |
|-----|--------|
| --wordlist | Specifies password list |

---

## Viewing Cracked Passwords

After cracking:

```
john --show hashes.txt
```

Example output:

```
password
```

---

## Common Wordlists

Some commonly used password lists:

```
/usr/share/wordlists/rockyou.txt
/usr/share/wordlists/fasttrack.txt
```

These contain millions of commonly used passwords.

---

## Real Pentesting Scenario

During a penetration test, password hashes may be obtained from:

- database dumps
- configuration files
- `/etc/shadow` on Linux systems
- password leaks

These hashes can then be tested using password cracking tools.

---

## Risk Impact

Weak passwords can allow attackers to:

- gain unauthorized access
- compromise user accounts
- escalate privileges
- access sensitive systems

---

## Mitigation & Defense

To prevent password cracking attacks:

- enforce strong password policies
- use salted password hashing
- implement multi-factor authentication
- monitor login attempts

---

## Reflection

Password cracking demonstrates how weak passwords can be exploited. It highlights the importance of strong authentication and proper password storage.
