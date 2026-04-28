---
tags: [tool, web, proxy, exploitation]
tool_name: "Burp Suite"
category: Web Exploitation
last_updated: 2024-01-01
---

# 🛠️ Burp Suite

## 📖 Description

> Suite d'outils de test de sécurité web. Proxy HTTP/S qui intercepte le trafic entre le navigateur et le serveur cible.

**Version gratuite :** Community Edition (suffisante pour THM)

---

## ⚙️ Configuration initiale

### Configurer le proxy Firefox

1. Paramètres Firefox → Réseau → Paramètres manuels du proxy
2. HTTP Proxy : `127.0.0.1` Port : `8080`
3. Installer le certificat Burp : visiter `http://burp` → CA Certificate

### Configurer FoxyProxy (recommandé)

1. Installer l'extension FoxyProxy dans Firefox
2. Créer un profil : `127.0.0.1:8080`
3. Toggle rapide ON/OFF

---

## 🚀 Modules principaux

### Proxy — Intercepter les requêtes

- `Proxy > Intercept > On`
- Naviguer sur la cible
- Modifier les requêtes à la volée
- `Forward` pour envoyer, `Drop` pour annuler

**Raccourcis clés :**
- `Ctrl+R` → Envoyer au Repeater
- `Ctrl+I` → Envoyer à l'Intruder

### Repeater — Rejouer et modifier des requêtes

```
Proxy → clic droit sur requête → Send to Repeater
```
- Modifier manuellement les paramètres
- Tester des payloads un par un
- Idéal pour : SQLi manuelle, XSS, IDOR

### Intruder — Attaques automatisées

**Types d'attaque :**
| Type | Usage |
|------|-------|
| Sniper | 1 payload set, 1 position |
| Battering Ram | 1 payload set, plusieurs positions identiques |
| Pitchfork | N payload sets, N positions (1:1) |
| Cluster Bomb | N payload sets, toutes combinaisons |

**Cas d'usage :** brute force login, fuzzing de paramètres

### Decoder — Encodage/décodage

- Base64, URL encode, HTML encode, Hex
- Hachage MD5, SHA1, SHA256

### Comparer (Comparer)

- Comparer deux requêtes/réponses
- Identifier les différences subtiles

---

## 💡 Tips & astuces

- Utiliser `Ctrl+U` pour URL encoder dans l'Intruder
- Le Scope (Target > Scope) évite de capturer tout le trafic
- Extensions utiles : Logger++, Autorize, ActiveScan++

---

## 🔗 Ressources

- [PortSwigger Web Academy](https://portswigger.net/web-security) ← pratique gratuite
- [Burp Suite Cheatsheet](https://github.com/Kitsun3Sec/Pentest-Cheat-Sheets/blob/master/CheatSheets/Burp%20Suite%20Cheat%20Sheet.pdf)
