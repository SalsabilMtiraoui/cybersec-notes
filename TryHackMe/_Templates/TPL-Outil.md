---
tags: [tool, "{{category}}"]
tool_name: "{{title}}"
category: 
last_updated: <% tp.date.now("YYYY-MM-DD") %>
---

# 🛠️ {{title}}

## 📖 Description

> En une phrase : à quoi sert cet outil et dans quel contexte on l'utilise.

**Catégorie :** Reconnaissance / Exploitation / Post-Exploitation / Forensics  
**Site officiel :** [lien](https://...)  
**Documentation :** [lien](https://...)

---

## ⚙️ Installation

```bash
# Kali Linux (souvent pré-installé)
sudo apt update && sudo apt install NOM -y

# Via pip (si outil Python)
pip3 install NOM

# Via git
git clone https://github.com/...
cd NOM && pip3 install -r requirements.txt
```

---

## 🚀 Commandes essentielles

### Utilisation de base

```bash
NOM [options] <cible>
```

### Cas d'usage 1 — [Nom du cas]

```bash
# Description de ce que fait cette commande
NOM --option1 --option2 <cible>
```

**Sortie typique :**
```
exemple de sortie
```

### Cas d'usage 2 — [Nom du cas]

```bash
NOM --flag <valeur> <cible>
```

### Cas d'usage 3 — [Nom du cas]

```bash
NOM --flag <valeur> <cible>
```

---

## 📋 Flags importants

| Flag | Description | Exemple |
|------|-------------|---------|
| `-h` | Affiche l'aide | `NOM -h` |
| | | |
| | | |

---

## 💡 Tips & astuces

- 
- 
- 

---

## ⚠️ Pièges courants

- 
- 

---

## 🔗 Utilisé dans ces rooms

```dataview
TABLE room AS "Room", date AS "Date"
FROM "01-TryHackMe"
WHERE contains(tools, this.tool_name)
```

---

## 📚 Ressources

- [Cheatsheet officielle](https://...)
- [HackTricks — NOM](https://book.hacktricks.xyz/...)
