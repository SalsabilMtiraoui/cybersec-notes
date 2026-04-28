---
tags: [methodology, reconnaissance, checklist]
---

# ✅ Reconnaissance Checklist

> Run through this systematically at the start of each room / engagement

---

## 🌐 Web

- [ ] Technologies identified (Wappalyzer, whatweb)
- [ ] HTTP headers analysed (`curl -I`)
- [ ] HTML source code inspected
- [ ] Robots.txt checked → `/robots.txt`
- [ ] Sitemap checked → `/sitemap.xml`
- [ ] Directories enumerated (Gobuster)
- [ ] Subdomains enumerated (if domain)
- [ ] Backup files searched (`.bak`, `.old`, `.swp`)
- [ ] Nikto run

## 🔌 Network

- [ ] Quick port scan (nmap -F)
- [ ] Full scan all ports (nmap -p-)
- [ ] Version detection (-sV)
- [ ] Default scripts (-sC)
- [ ] UDP scan if needed

## 🗂️ Specific Services

### FTP (21)
- [ ] Anonymous login tested (`anonymous` / `anonymous`)
- [ ] Contents listed

### SSH (22)
- [ ] Version noted (vulnerabilities?)
- [ ] Brute force if usernames known

### SMB (445)
- [ ] Shares listed (`smbclient -L`)
- [ ] Anonymous access tested
- [ ] `enum4linux -A` run

### HTTP/HTTPS (80/443)
- [ ] See Web checklist above

### Database (3306, 5432, 27017...)
- [ ] Unauthenticated connection tested
- [ ] Default credentials tested
