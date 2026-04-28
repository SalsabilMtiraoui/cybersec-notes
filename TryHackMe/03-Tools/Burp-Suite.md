---
tags: [tool, web, proxy, exploitation]
tool_name: "Burp Suite"
category: Web Exploitation
last_updated: 2024-01-01
---

# 🛠️ Burp Suite

## 📖 Description

> Suite of web security testing tools. HTTP/S proxy that intercepts traffic between the browser and the target server.

**Free version:** Community Edition (sufficient for THM)

---

## ⚙️ Initial Setup

### Configure Firefox proxy

1. Firefox Settings → Network → Manual proxy settings
2. HTTP Proxy: `127.0.0.1` Port: `8080`
3. Install Burp certificate: visit `http://burp` → CA Certificate

### Configure FoxyProxy (recommended)

1. Install FoxyProxy extension in Firefox
2. Create profile: `127.0.0.1:8080`
3. Quick ON/OFF toggle

---

## 🚀 Main Modules

### Proxy — Intercept Requests

- `Proxy > Intercept > On`
- Browse to the target
- Modify requests on the fly
- `Forward` to send, `Drop` to cancel

**Key shortcuts:**
- `Ctrl+R` → Send to Repeater
- `Ctrl+I` → Send to Intruder

### Repeater — Replay and Modify Requests

```
Proxy → right-click on request → Send to Repeater
```
- Manually modify parameters
- Test payloads one by one
- Ideal for: manual SQLi, XSS, IDOR

### Intruder — Automated Attacks

**Attack types:**
| Type | Usage |
|------|-------|
| Sniper | 1 payload set, 1 position |
| Battering Ram | 1 payload set, multiple identical positions |
| Pitchfork | N payload sets, N positions (1:1) |
| Cluster Bomb | N payload sets, all combinations |

**Use cases:** login brute force, parameter fuzzing

### Decoder — Encoding/Decoding

- Base64, URL encode, HTML encode, Hex
- Hashing: MD5, SHA1, SHA256

---

## 💡 Tips & Tricks

- Use `Ctrl+U` to URL-encode in Intruder
- Scope (Target > Scope) prevents capturing all traffic
- Useful extensions: Logger++, Autorize, ActiveScan++

---

## 🔗 Resources

- [PortSwigger Web Academy](https://portswigger.net/web-security) ← free hands-on practice
- [Burp Suite Cheatsheet](https://github.com/Kitsun3Sec/Pentest-Cheat-Sheets/blob/master/CheatSheets/Burp%20Suite%20Cheat%20Sheet.pdf)
