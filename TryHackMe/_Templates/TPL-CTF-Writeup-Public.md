---
tags: [writeup, ctf, tryhackme, "{{difficulty}}", "{{category}}"]
room: "{{title}}"
date: <% tp.date.now("YYYY-MM-DD") %>
published: true
difficulty: 
category: 
---

# 🚩 Writeup: {{title}} — TryHackMe

**Difficulty:** Medium  
**Category:** Web Exploitation  
**Date:** <% tp.date.now("DD MMMM YYYY") %>  
**Author:** [Your Name](https://tryhackme.com/p/YOURUSERNAME)

---

## 📋 Summary

> 3-4 sentences: context of the room, what it simulates, what you learn. Should make the reader want to continue.

---

## 🌐 Environment

| Element | Detail |
|---------|--------|
| Target OS | Ubuntu 20.04 |
| Target IP | `10.10.X.X` |
| Exposed Services | HTTP (80), SSH (22) |
| Tools Used | Nmap, Gobuster, Burp Suite |

---

## 🔍 Step 1 — Reconnaissance

First systematic step: identify the attack surface.

```bash
nmap -sC -sV -oN nmap.txt 10.10.X.X
```

The results show [describe what you see and why it is interesting].

---

## 📂 Step 2 — Enumeration

[Describe your logical reasoning — why you choose to explore a particular service first]

```bash
gobuster dir -u http://10.10.X.X -w /usr/share/wordlists/dirb/common.txt
```

I discovered [what you found], which led me to [next step].

---

## 💥 Step 3 — Exploitation

### Vulnerability Identification

[Explain the vulnerability in plain language — mechanism, why it exists]

### Exploitation

```bash
# Payload / command used
```

[Describe what happens, the result obtained]

---

## 🔼 Step 4 — Privilege Escalation

[Describe how you move from user to root / SYSTEM]

```bash
sudo -l
# or
find / -perm -4000 2>/dev/null
```

[Explain the privesc vector and why it works]

---

## 🏳️ Flags Obtained

| Flag | Location |
|------|----------|
| `THM{user_flag}` | `/home/user/user.txt` |
| `THM{root_flag}` | `/root/root.txt` |

---

## 📚 What I Learned

- **[Concept 1]:** explanation
- **[Concept 2]:** explanation
- **[Concept 3]:** explanation

---

## 🛡️ Remediation Recommendations

> Bonus section appreciated by recruiters — shows you also think like a defender

- Update [vulnerable service] to version X
- Disable [unnecessary feature]
- Implement [security control]

---

## 🔗 References

- [Official documentation](https://...)
- [CVE-XXXX-XXXX](https://nvd.nist.gov/vuln/detail/CVE-XXXX-XXXX)
