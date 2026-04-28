---
tags: [tool, web, enumeration]
tool_name: "Gobuster"
category: Web Enumeration
last_updated: 2024-01-01
---

# 🛠️ Gobuster

## 📖 Description

> Brute-force tool for web directories/files, DNS subdomains, and virtual hosts.

---

## 🚀 Essential Commands

### Directory enumeration (most common)

```bash
gobuster dir -u http://<IP> -w /usr/share/wordlists/dirb/common.txt
```

### With file extensions

```bash
gobuster dir -u http://<IP> -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x php,html,txt,bak
```

### With file output

```bash
gobuster dir -u http://<IP> -w /usr/share/wordlists/dirb/common.txt -o gobuster_results.txt
```

### DNS enumeration (subdomains)

```bash
gobuster dns -d domain.com -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt
```

### Virtual hosts

```bash
gobuster vhost -u http://<IP> -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt
```

---

## 📋 Important Flags

| Flag | Description |
|------|-------------|
| `-u` | Target URL |
| `-w` | Wordlist |
| `-x` | Extensions (php,html,txt) |
| `-o` | Output file |
| `-t` | Threads (default 10) |
| `-s` | Status codes to show |
| `-b` | Status codes to ignore |
| `--timeout` | Per-request timeout |
| `-k` | Ignore SSL errors |

---

## 💡 Recommended Wordlists

```bash
# Small (fast)
/usr/share/wordlists/dirb/common.txt

# Medium (good balance)
/usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt

# Large (via SecLists)
/usr/share/wordlists/SecLists/Discovery/Web-Content/raft-large-directories.txt
```

---

## 🔗 Resources

- [GitHub Gobuster](https://github.com/OJ/gobuster)
- [SecLists Wordlists](https://github.com/danielmiessler/SecLists)
