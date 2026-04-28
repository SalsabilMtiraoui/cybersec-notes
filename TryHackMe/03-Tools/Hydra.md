---
tags: [tool, brute-force, authentication]
tool_name: "Hydra"
category: Brute Force
last_updated: 2024-01-01
---

# 🛠️ Hydra

## 📖 Description

> Fast, parallelised brute-force tool supporting a large number of authentication protocols.

---

## 🚀 Essential Commands

### SSH

```bash
hydra -l <user> -P /usr/share/wordlists/rockyou.txt ssh://<IP>
hydra -L users.txt -P passwords.txt ssh://<IP> -t 4
```

### HTTP POST (login form)

```bash
hydra -l admin -P rockyou.txt <IP> http-post-form "/login:username=^USER^&password=^PASS^:F=Invalid credentials"
# F= : message indicating FAILURE
# S= : message indicating SUCCESS
```

### HTTP GET (basic auth)

```bash
hydra -l admin -P rockyou.txt <IP> http-get /admin
```

### FTP

```bash
hydra -l <user> -P rockyou.txt ftp://<IP>
```

### SMB

```bash
hydra -l <user> -P rockyou.txt smb://<IP>
```

---

## 📋 Important Flags

| Flag | Description |
|------|-------------|
| `-l` | Single username |
| `-L` | Username file |
| `-p` | Single password |
| `-P` | Password file |
| `-t` | Parallel threads |
| `-s` | Specific port |
| `-f` | Stop on first success |
| `-o` | Output file |
| `-v` | Verbose |

---

## 💡 Tips

- `rockyou.txt` is at `/usr/share/wordlists/rockyou.txt` (gunzip if needed)
- Limit threads (`-t 4`) for SSH to avoid rate limiting
- For HTTP POST: identify form fields with Burp Suite first

---

## 🔗 Resources

- [Hydra cheatsheet](https://github.com/frizb/Hydra-Cheatsheet)
