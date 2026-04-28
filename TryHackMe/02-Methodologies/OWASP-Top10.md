---
tags: [methodology, web, owasp]
---

# 🔟 OWASP Top 10 (2021)

> Essential reference for the 10 most critical security risks in web applications.

---

| # | Category | Examples |
|---|----------|---------|
| A01 | **Broken Access Control** | IDOR, privilege escalation, misconfigured CORS |
| A02 | **Cryptographic Failures** | Sensitive data in plaintext, MD5/SHA1, unencrypted HTTP |
| A03 | **Injection** | SQLi, XSS, LDAP Injection, Command Injection |
| A04 | **Insecure Design** | No rate limiting, flawed business logic |
| A05 | **Security Misconfiguration** | Unnecessary open ports, default accounts, verbose errors |
| A06 | **Vulnerable Components** | Outdated libraries, unpatched CVEs |
| A07 | **Auth Failures** | Brute force, session fixation, weak tokens |
| A08 | **Software & Data Integrity** | Insecure CI/CD, unreliable deserialisation |
| A09 | **Logging Failures** | No logs, unmonitored logs |
| A10 | **SSRF** | Accessing internal services through the app |

---

## A01 — Broken Access Control

```
Test: change the ID in the URL → /user/1234 → /user/1235
Test: access /admin without being an admin
Test: modify the role in a cookie/JWT
```
See [[../04-Vulnerabilities/IDOR]] (to create)

## A03 — Injection

```
SQLi → [[../04-Vulnerabilities/SQLi]]
XSS  → [[../04-Vulnerabilities/XSS]]
```

---

## 🔗 Resources

- [OWASP Top 10 official](https://owasp.org/Top10/)
- [OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)
