---
tags: [tool, network, analysis]
tool_name: "Wireshark"
category: Network Analysis
last_updated: 2024-01-01
---

# 🛠️ Wireshark

## 📖 Description

> Graphical network packet analyser. Captures and analyses network traffic in real time.

---

## 🚀 Essential Filters

### Filter by protocol

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

### Filter by IP

```
ip.addr == 10.10.X.X
ip.src == 10.10.X.X
ip.dst == 10.10.X.X
```

### Filter by port

```
tcp.port == 80
udp.port == 53
```

### Combined filters

```
http && ip.addr == 10.10.X.X
tcp.port == 80 || tcp.port == 443
!(arp || dns || icmp)    # Exclude noise
```

### Search within content

```
tcp contains "password"
http.request.uri contains "login"
frame contains "flag"
```

---

## 💡 Tips & Tricks

- `Follow TCP Stream`: reconstruct a full conversation
- `Export Objects > HTTP`: extract transferred files
- `Statistics > Protocol Hierarchy`: traffic overview
- `Statistics > Conversations`: who is talking to whom

---

## 🔗 Resources

- [Wireshark Display Filters](https://wiki.wireshark.org/DisplayFilters)
