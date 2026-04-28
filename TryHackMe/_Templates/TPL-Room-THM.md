---
tags: [tryhackme, "{{difficulty}}", "{{category}}"]
room: "{{title}}"
date: <% tp.date.now("YYYY-MM-DD") %>
status: 🔄 In Progress
difficulty: 
category: 
target_ip: 
---

# 🏠 {{title}}

## 📌 Informations générales

| Champ | Valeur |
|-------|--------|
| **Lien THM** | [Ouvrir la room](https://tryhackme.com/room/SLUG) |
| **Difficulté** | Easy / Medium / Hard |
| **Catégorie** | Web / Network / Linux / Windows / Crypto |
| **IP cible** | `10.10.X.X` |
| **Temps passé** | Xh Xmin |
| **Date** | <% tp.date.now("DD/MM/YYYY") %> |

---

## 🎯 Objectifs de la room

> Résume ici en quelques phrases ce que la room va enseigner et ce qu'on va pratiquer.

- [ ] Objectif 1
- [ ] Objectif 2
- [ ] Objectif 3

---

## 🔍 Phase 1 — Reconnaissance

### Scan Nmap

```bash
# Scan initial rapide
nmap -sV -sC -oN nmap/initial.txt 10.10.X.X

# Scan complet (tous ports)
nmap -p- -T4 -oN nmap/full.txt 10.10.X.X
```

**Résultats :**

| Port | État | Service | Version |
|------|------|---------|---------|
| 22 | open | ssh | OpenSSH X.X |
| 80 | open | http | Apache X.X |

**Observations :**
> Ce que tu remarques, ce qui semble intéressant

---

### Énumération Web (si applicable)

```bash
# Gobuster — découverte de répertoires
gobuster dir -u http://10.10.X.X -w /usr/share/wordlists/dirb/common.txt -o gobuster.txt

# Nikto — scan de vulnérabilités web
nikto -h http://10.10.X.X
```

**Répertoires / fichiers trouvés :**
- `/admin` — 
- `/login` — 

---

## 🔐 Phase 2 — Énumération approfondie

> Détaille ici les services identifiés et comment tu les explores

### Service X (ex: SMB, FTP, HTTP)

```bash
# commandes utilisées
```

**Informations récoltées :**
- 
- 

---

## 💥 Phase 3 — Exploitation

### Vulnérabilité identifiée

**Type :** (ex: SQLi, RCE, Buffer Overflow, Misconfiguration…)  
**CVE :** CVE-XXXX-XXXX (si applicable)  
**Pourquoi ça marche :** 
> Explique le mécanisme de la vulnérabilité — c'est ce qui montre ta compréhension au recruteur

### Exploitation

```bash
# Commandes d'exploitation
```

**Résultat obtenu :**
> Décris ce qui s'est passé, ce que tu as obtenu

**Erreurs rencontrées et solutions :**
> Document tes galères, c'est formateur et valorisant

---

## 🔼 Phase 4 — Élévation de privilèges

### Vecteur de privesc

**Méthode :** (ex: SUID binary, cron job, sudo misconfiguration, kernel exploit…)

```bash
# Énumération
./linpeas.sh
find / -perm -4000 2>/dev/null

# Exploitation
```

**Résultat :** Accès root / SYSTEM obtenu ✓

---

## 🏳️ Flags

| Flag | Valeur | Localisation |
|------|--------|--------------|
| user.txt | `THM{XXXXXXXXXXXXXXXX}` | `/home/user/` |
| root.txt | `THM{XXXXXXXXXXXXXXXX}` | `/root/` |

---

## 📚 Concepts clés appris

> Cette section est ce que les recruteurs lisent en priorité

- **Concept 1 :** explication en tes propres mots
- **Concept 2 :** 
- **Concept 3 :** 

---

## 🔧 Outils utilisés

| Outil | Usage dans cette room |
|-------|-----------------------|
| [[Nmap]] | Scan initial des ports |
| [[Gobuster]] | Énumération des répertoires web |

---

## 💡 Points à retenir / Pièges

> Ce que tu aurais aimé savoir avant, ce qu'il ne faut pas oublier

- ⚠️ 
- 💡 

---

## 🔗 Ressources consultées

- [Lien 1](https://...)
- [Lien 2](https://...)

---

*Status final : 🔄 In Progress → changer en ✅ Done une fois terminé*
