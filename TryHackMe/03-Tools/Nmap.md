---
tags: [tool, reconnaissance, network]
tool_name: "Nmap"
category: Reconnaissance
last_updated: 2024-01-01
---

# 🛠️ Nmap — Network Mapper

## 📖 Description

> Network port scanner that discovers active hosts, services, and versions on a network.

**Official site:** [nmap.org](https://nmap.org)

---

## 🚀 Essential Commands

### Basic scan (most common in CTFs)

```bash
nmap -sC -sV -oN nmap_initial.txt <IP>
# -sC : default scripts
# -sV : version detection
# -oN : save in normal format
```

### All ports scan

```bash
nmap -p- -T4 --min-rate 5000 -oN nmap_full.txt <IP>
# -p- : all 65535 ports
# -T4 : aggressive speed
# --min-rate : at least 5000 packets/sec
```

### UDP scan

```bash
sudo nmap -sU --top-ports 20 <IP>
```

### Stealth scan (SYN scan)

```bash
sudo nmap -sS <IP>
```

### OS detection

```bash
sudo nmap -O <IP>
```

### Scan with specific NSE scripts

```bash
nmap --script vuln <IP>
nmap --script smb-enum-shares <IP>
nmap --script http-enum <IP>
```

---

## 📋 Important Flags

| Flag | Description |
|------|-------------|
| `-sC` | Default NSE scripts |
| `-sV` | Service version detection |
| `-sS` | SYN scan (stealth, requires root) |
| `-sU` | UDP scan |
| `-p-` | All ports (1-65535) |
| `-p 80,443` | Specific ports |
| `-T1` to `-T5` | Speed (1=slow/stealth, 5=fast/noisy) |
| `-oN` | Normal output format |
| `-oX` | XML output format |
| `-oG` | Grepable output format |
| `-oA` | All output formats |
| `-A` | OS + version + scripts + traceroute |
| `--min-rate` | Minimum packets/sec |
| `-v` / `-vv` | Verbosity |

---

## 💡 Tips & Tricks

- Always save results with `-oN` or `-oA`
- In CTFs, start with a quick scan, then run a full scan in parallel
- `vuln` scripts take time but reveal a lot
- `grep "open" nmap_full.txt` to quickly filter open ports

---

## 🔗 Resources

- [Nmap Cheat Sheet — StationX](https://www.stationx.net/nmap-cheat-sheet/)
- [HackTricks — Nmap](https://book.hacktricks.xyz/generic-methodologies-and-resources/pentesting-network/nmap-cheatsheet-hack-tricks)
