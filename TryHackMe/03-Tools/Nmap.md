---
tags: [tool, reconnaissance, network]
tool_name: "Nmap"
category: Reconnaissance
last_updated: 2024-01-01
---

# 🛠️ Nmap — Network Mapper

## 📖 Description

> Scanner de ports réseau permettant de découvrir les hôtes, services et versions actifs sur un réseau.

**Site officiel :** [nmap.org](https://nmap.org)

---

## 🚀 Commandes essentielles

### Scan de base (le plus courant en CTF)

```bash
nmap -sC -sV -oN nmap_initial.txt <IP>
# -sC : scripts par défaut
# -sV : détection de version
# -oN : sauvegarde en format normal
```

### Scan tous ports

```bash
nmap -p- -T4 --min-rate 5000 -oN nmap_full.txt <IP>
# -p- : tous les 65535 ports
# -T4 : vitesse agressive
# --min-rate : au moins 5000 paquets/sec
```

### Scan UDP

```bash
sudo nmap -sU --top-ports 20 <IP>
```

### Scan furtif (SYN scan)

```bash
sudo nmap -sS <IP>
```

### Détection OS

```bash
sudo nmap -O <IP>
```

### Scan avec scripts NSE spécifiques

```bash
nmap --script vuln <IP>
nmap --script smb-enum-shares <IP>
nmap --script http-enum <IP>
```

---

## 📋 Flags importants

| Flag | Description |
|------|-------------|
| `-sC` | Scripts NSE par défaut |
| `-sV` | Détection des versions |
| `-sS` | SYN scan (furtif, nécessite root) |
| `-sU` | Scan UDP |
| `-p-` | Tous les ports (1-65535) |
| `-p 80,443` | Ports spécifiques |
| `-T1` à `-T5` | Vitesse (1=lent/furtif, 5=rapide/bruyant) |
| `-oN` | Output format normal |
| `-oX` | Output format XML |
| `-oG` | Output format grepable |
| `-oA` | Output tous les formats |
| `-A` | OS + version + scripts + traceroute |
| `--min-rate` | Paquets/sec minimum |
| `-v` / `-vv` | Verbosité |

---

## 💡 Tips & astuces

- Toujours sauvegarder les résultats avec `-oN` ou `-oA`
- En CTF, commencer par un scan rapide, puis scan complet en parallèle
- Les scripts `vuln` peuvent prendre du temps mais révèlent beaucoup
- `grep "open" nmap_full.txt` pour filtrer rapidement les ports ouverts

---

## 🔗 Ressources

- [Nmap Cheat Sheet — StationX](https://www.stationx.net/nmap-cheat-sheet/)
- [HackTricks — Nmap](https://book.hacktricks.xyz/generic-methodologies-and-resources/pentesting-network/nmap-cheatsheet-hack-tricks)
