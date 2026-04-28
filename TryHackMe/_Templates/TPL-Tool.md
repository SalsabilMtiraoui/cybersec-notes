---
tags: [tool, "{{category}}"]
tool_name: "{{title}}"
category: 
last_updated: <% tp.date.now("YYYY-MM-DD") %>
---

# 🛠️ {{title}}

## 📖 Description

> One sentence: what this tool does and in what context it is used.

**Category:** Reconnaissance / Exploitation / Post-Exploitation / Forensics  
**Official site:** [link](https://...)  
**Documentation:** [link](https://...)

---

## ⚙️ Installation

```bash
# Kali Linux (often pre-installed)
sudo apt update && sudo apt install TOOLNAME -y

# Via pip (Python tool)
pip3 install TOOLNAME

# Via git
git clone https://github.com/...
cd TOOLNAME && pip3 install -r requirements.txt
```

---

## 🚀 Essential Commands

### Basic usage

```bash
TOOLNAME [options] <target>
```

### Use case 1 — [Name]

```bash
# Description of what this command does
TOOLNAME --option1 --option2 <target>
```

**Typical output:**
```
example output
```

### Use case 2 — [Name]

```bash
TOOLNAME --flag <value> <target>
```

### Use case 3 — [Name]

```bash
TOOLNAME --flag <value> <target>
```

---

## 📋 Important Flags

| Flag | Description | Example |
|------|-------------|---------|
| `-h` | Display help | `TOOLNAME -h` |
| | | |
| | | |

---

## 💡 Tips & Tricks

- 
- 
- 

---

## ⚠️ Common Pitfalls

- 
- 

---

## 🔗 Used in These Rooms

```dataview
TABLE room AS "Room", date AS "Date"
FROM "01-TryHackMe"
WHERE contains(tools, this.tool_name)
```

---

## 📚 Resources

- [Official cheatsheet](https://...)
- [HackTricks — TOOLNAME](https://book.hacktricks.xyz/...)
