# 🗺️ Dashboard — CyberSec Notes

## 📊 JR Pentester Path Progress

```dataview
TABLE room AS "Room", difficulty AS "Difficulty", status AS "Status", date AS "Date"
FROM "01-TryHackMe/JR-Pentester-Path"
WHERE file.name != "_INDEX"
SORT date DESC
```

---

## ✅ Completed Rooms

```dataview
TABLE room AS "Room", category AS "Category", date AS "Date"
FROM "01-TryHackMe"
WHERE status = "✅ Done"
SORT date DESC
```

---

## 🔄 In Progress

```dataview
LIST
FROM "01-TryHackMe"
WHERE status = "🔄 In Progress"
```

---

## 🛠️ Documented Tools

```dataview
TABLE file.mtime AS "Last Modified"
FROM "03-Tools"
SORT file.name ASC
```

---

## 📅 Recent Activity

```dataview
TABLE file.mtime AS "Modified"
FROM "01-TryHackMe" OR "04-Vulnerabilities"
SORT file.mtime DESC
LIMIT 10
```
