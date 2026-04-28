---
tags: [methodology, reconnaissance, checklist]
---

# ✅ Checklist Reconnaissance

> À dérouler systématiquement au début de chaque room / engagement

---

## 🌐 Web

- [ ] Technologies identifiées (Wappalyzer, whatweb)
- [ ] En-têtes HTTP analysés (`curl -I`)
- [ ] Code source HTML inspecté
- [ ] Robots.txt consulté → `/robots.txt`
- [ ] Sitemap consulté → `/sitemap.xml`
- [ ] Répertoires énumérés (Gobuster)
- [ ] Sous-domaines énumérés (si domaine)
- [ ] Fichiers de backup cherchés (`.bak`, `.old`, `.swp`)
- [ ] Nikto lancé

## 🔌 Réseau

- [ ] Scan de ports rapide (nmap -F)
- [ ] Scan complet tous ports (nmap -p-)
- [ ] Détection de versions (-sV)
- [ ] Scripts par défaut (-sC)
- [ ] Scan UDP si nécessaire

## 🗂️ Services spécifiques

### FTP (21)
- [ ] Login anonyme testé (`anonymous` / `anonymous`)
- [ ] Contenu listé

### SSH (22)
- [ ] Version notée (vulnérabilités?)
- [ ] Brute force si usernames connus

### SMB (445)
- [ ] Shares listés (`smbclient -L`)
- [ ] Accès anonyme testé
- [ ] `enum4linux -A` lancé

### HTTP/HTTPS (80/443)
- [ ] Voir checklist Web ci-dessus

### Base de données (3306, 5432, 27017...)
- [ ] Connexion sans auth testée
- [ ] Credentials par défaut testés
