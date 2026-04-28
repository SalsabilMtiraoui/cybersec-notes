---
tags: [writeup, ctf, tryhackme, "{{difficulty}}", "{{category}}"]
room: "{{title}}"
date: <% tp.date.now("YYYY-MM-DD") %>
published: true
difficulty: 
category: 
---

# Writeup : {{title}} — TryHackMe

**Difficulty :** Medium  
**Catégorie :** Web Exploitation  
**Date :** <% tp.date.now("DD MMMM YYYY") %>  
**Auteure :** [Ton Prénom](https://tryhackme.com/p/TONPSEUDO)

---

## Summary

> En 3-4 phrases : contexte de la room, ce qu'elle simule, ce qu'on y apprend. Doit donner envie de lire la suite.

---

##  Environnement

| Élément | Détail |
|---------|--------|
| OS cible | Ubuntu 20.04 |
| IP cible | `10.10.X.X` |
| Services exposés | HTTP (80), SSH (22) |
| Outils utilisés | Nmap, Gobuster, Burp Suite |

---

## 🔍 Étape 1 — Reconnaissance

Première étape systématique : identifier les surfaces d'attaque.

```bash
nmap -sC -sV -oN nmap.txt 10.10.X.X
```

Les résultats montrent [décrire ce que tu vois et pourquoi c'est intéressant].

---

## 📂 Étape 2 — Énumération

[Décris ta démarche logique — pourquoi tu choisis d'explorer tel service en premier]

```bash
gobuster dir -u http://10.10.X.X -w /usr/share/wordlists/dirb/common.txt
```

J'ai découvert [ce que tu as trouvé], ce qui m'a conduite à [prochaine étape].

---

## 💥 Étape 3 — Exploitation

### Identification de la vulnérabilité

[Explique la vulnérabilité en langage clair — mécanisme, pourquoi elle existe]

### Exploitation

```bash
# Payload / commande utilisée
```

[Décris ce qui se passe, le résultat obtenu]

---

## 🔼 Étape 4 — Élévation de privilèges

[Décris comment tu passes de user à root / SYSTEM]

```bash
sudo -l
# ou
find / -perm -4000 2>/dev/null
```

[Explique le vecteur de privesc et pourquoi il fonctionne]

---

## 🏳️ Flags obtenus

| Flag | Localisation |
|------|--------------|
| `THM{user_flag}` | `/home/user/user.txt` |
| `THM{root_flag}` | `/root/root.txt` |

---

## 📚 Ce que j'ai appris

- **[Concept 1] :** explication
- **[Concept 2] :** explication
- **[Concept 3] :** explication

---

## 🛡️ Recommandations de remédiation

> Section bonus appréciée des recruteurs — montre que tu penses en défenseur aussi

- Mettre à jour [service vulnérable] vers la version X
- Désactiver [fonctionnalité inutile]
- Implémenter [contrôle de sécurité]

---

## 🔗 Références

- [Documentation officielle](https://...)
- [CVE-XXXX-XXXX](https://nvd.nist.gov/vuln/detail/CVE-XXXX-XXXX)
