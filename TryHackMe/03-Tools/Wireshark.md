---
tags: [tool, network, analysis]
tool_name: "Wireshark"
category: Network Analysis
last_updated: 2024-01-01
---

# 🛠️ Wireshark

## 📖 Description

> Analyseur de paquets réseau graphique. Capture et analyse le trafic réseau en temps réel.

---

## 🚀 Filtres essentiels

### Filtres par protocole

```
http
dns
ftp
ssh
tcp
udp
icmp
smb
```

### Filtres par IP

```
ip.addr == 10.10.X.X
ip.src == 10.10.X.X
ip.dst == 10.10.X.X
```

### Filtres par port

```
tcp.port == 80
udp.port == 53
```

### Filtres combinés

```
http && ip.addr == 10.10.X.X
tcp.port == 80 || tcp.port == 443
!(arp || dns || icmp)    # Exclure le bruit
```

### Rechercher dans le contenu

```
tcp contains "password"
http.request.uri contains "login"
frame contains "flag"
```

---

## 💡 Astuces

- `Follow TCP Stream` : reconstituer une conversation complète
- `Export Objects > HTTP` : extraire fichiers transférés
- `Statistics > Protocol Hierarchy` : vue d'ensemble du trafic
- `Statistics > Conversations` : qui parle à qui

---

## 🔗 Ressources

- [Wireshark Display Filters](https://wiki.wireshark.org/DisplayFilters)
