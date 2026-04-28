---
tags: [methodology, web, owasp]
---

# 🔟 OWASP Top 10 (2021)

> Référence incontournable des 10 risques de sécurité les plus critiques pour les applications web.

---

| # | Catégorie | Exemples |
|---|-----------|---------|
| A01 | **Broken Access Control** | IDOR, escalade de privilèges, CORS mal configuré |
| A02 | **Cryptographic Failures** | Données sensibles en clair, MD5/SHA1, HTTP non chiffré |
| A03 | **Injection** | SQLi, XSS, LDAP Injection, Command Injection |
| A04 | **Insecure Design** | Absence de rate limiting, logique métier défaillante |
| A05 | **Security Misconfiguration** | Ports ouverts inutiles, comptes par défaut, verbose errors |
| A06 | **Vulnerable Components** | Bibliothèques obsolètes, CVEs non patchés |
| A07 | **Auth Failures** | Brute force, session fixation, tokens faibles |
| A08 | **Software & Data Integrity** | CI/CD non sécurisé, désérialisation non fiable |
| A09 | **Logging Failures** | Absence de logs, logs non monitorés |
| A10 | **SSRF** | Accès aux services internes via l'appli |

---

## A01 — Broken Access Control

```
Test : changer l'ID dans l'URL → /user/1234 → /user/1235
Test : accéder à /admin sans être admin
Test : modifier le rôle dans un cookie/JWT
```
Voir [[../04-Vulnerabilities/IDOR]] (à créer)

## A03 — Injection

```
SQLi → [[../04-Vulnerabilities/SQLi]]
XSS  → [[../04-Vulnerabilities/XSS]]
```

---

## 🔗 Ressources

- [OWASP Top 10 officiel](https://owasp.org/Top10/)
- [OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)
