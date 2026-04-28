---
tags: [tryhackme, "{{difficulty}}", "{{category}}"]
room: "{{title}}"
date: <% tp.date.now("YYYY-MM-DD") %>
status: 🔄 In Progress
difficulty: 
category: 
target_ip: 
---

# 🏠 {{title}}

## 📌 General Information

| Field | Value |
|-------|-------|
| **THM Link** | [Open room](https://tryhackme.com/room/SLUG) |
| **Difficulty** | Easy / Medium / Hard |
| **Category** | Web / Network / Linux / Windows / Crypto |
| **Target IP** | `10.10.X.X` |
| **Time Spent** | Xh Xmin |
| **Date** | <% tp.date.now("DD/MM/YYYY") %> |

---

## 🎯 Room Objectives

> Summarise in a few sentences what the room teaches and what we will practice.

- [ ] Objective 1
- [ ] Objective 2
- [ ] Objective 3

---

## 🔍 Phase 1 — Reconnaissance

### Nmap Scan

```bash
# Quick initial scan
nmap -sV -sC -oN nmap/initial.txt 10.10.X.X

# Full scan (all ports)
nmap -p- -T4 -oN nmap/full.txt 10.10.X.X
```

**Results:**

| Port | State | Service | Version |
|------|-------|---------|---------|
| 22 | open | ssh | OpenSSH X.X |
| 80 | open | http | Apache X.X |

**Observations:**
> What you notice, what looks interesting

---

### Web Enumeration (if applicable)

```bash
# Gobuster — directory discovery
gobuster dir -u http://10.10.X.X -w /usr/share/wordlists/dirb/common.txt -o gobuster.txt

# Nikto — web vulnerability scan
nikto -h http://10.10.X.X
```

**Directories / files found:**
- `/admin` — 
- `/login` — 

---

## 🔐 Phase 2 — Deeper Enumeration

> Detail the identified services and how you explore them

### Service X (e.g. SMB, FTP, HTTP)

```bash
# commands used
```

**Information gathered:**
- 
- 

---

## 💥 Phase 3 — Exploitation

### Identified Vulnerability

**Type:** (e.g. SQLi, RCE, Buffer Overflow, Misconfiguration…)  
**CVE:** CVE-XXXX-XXXX (if applicable)  
**Why it works:**
> Explain the vulnerability mechanism — this is what demonstrates your understanding to a recruiter

### Exploitation

```bash
# Exploitation commands
```

**Result:**
> Describe what happened, what you obtained

**Errors encountered and solutions:**
> Document your struggles — it's educational and shows problem-solving

---

## 🔼 Phase 4 — Privilege Escalation

### PrivEsc Vector

**Method:** (e.g. SUID binary, cron job, sudo misconfiguration, kernel exploit…)

```bash
# Enumeration
./linpeas.sh
find / -perm -4000 2>/dev/null

# Exploitation
```

**Result:** Root / SYSTEM access obtained ✓

---

## 🏳️ Flags

| Flag | Value | Location |
|------|-------|----------|
| user.txt | `THM{XXXXXXXXXXXXXXXX}` | `/home/user/` |
| root.txt | `THM{XXXXXXXXXXXXXXXX}` | `/root/` |

---

## 📚 Key Concepts Learned

> This section is what recruiters read first

- **Concept 1:** explanation in your own words
- **Concept 2:** 
- **Concept 3:** 

---

## 🔧 Tools Used

| Tool | Usage in this room |
|------|--------------------|
| [[Nmap]] | Initial port scan |
| [[Gobuster]] | Web directory enumeration |

---

## 💡 Key Takeaways / Pitfalls

> What you wish you knew beforehand, what not to forget

- ⚠️ 
- 💡 

---

## 🔗 Resources Consulted

- [Link 1](https://...)
- [Link 2](https://...)

---

*Final status: 🔄 In Progress → change to ✅ Done once complete*
