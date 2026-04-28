---
tags: [tool, web, enumeration]
tool_name: "Gobuster"
category: Web Enumeration
last_updated: 2024-01-01
---

# 🛠️ Gobuster

## 📖 Description

> Outil de brute-force de répertoires/fichiers web, sous-domaines DNS et virtual hosts.

---

## 🚀 Commandes essentielles

### Enumération de répertoires (le plus courant)

```bash
gobuster dir -u http://<IP> -w /usr/share/wordlists/dirb/common.txt
```

### Avec extensions de fichiers

```bash
gobuster dir -u http://<IP> -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x php,html,txt,bak
```

### Avec output fichier

```bash
gobuster dir -u http://<IP> -w /usr/share/wordlists/dirb/common.txt -o gobuster_results.txt
```

### Enumération DNS (sous-domaines)

```bash
gobuster dns -d domaine.com -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt
```

### Virtual hosts

```bash
gobuster vhost -u http://<IP> -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt
```

---

## 📋 Flags importants

| Flag | Description |
|------|-------------|
| `-u` | URL cible |
| `-w` | Wordlist |
| `-x` | Extensions (php,html,txt) |
| `-o` | Output fichier |
| `-t` | Threads (défaut 10) |
| `-s` | Status codes à afficher |
| `-b` | Status codes à ignorer |
| `--timeout` | Timeout par requête |
| `-k` | Ignorer les erreurs SSL |

---

## 💡 Wordlists recommandées

```bash
# Petite (rapide)
/usr/share/wordlists/dirb/common.txt

# Moyenne (bon équilibre)
/usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt

# Grande (via SecLists)
/usr/share/wordlists/SecLists/Discovery/Web-Content/raft-large-directories.txt
```

---

## 🔗 Ressources

- [GitHub Gobuster](https://github.com/OJ/gobuster)
- [SecLists Wordlists](https://github.com/danielmiessler/SecLists)
