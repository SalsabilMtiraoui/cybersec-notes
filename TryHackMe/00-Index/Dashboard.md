# 🗺️ Dashboard — CyberSec Notes

## 📊 Progression JR Pentester Path

```dataview
TABLE room AS "Room", difficulty AS "Difficulté", status AS "Statut", date AS "Date"
FROM "01-TryHackMe/JR-Pentester-Path"
WHERE file.name != "_INDEX"
SORT date DESC
```

---

## ✅ Rooms terminées

```dataview
TABLE room AS "Room", category AS "Catégorie", date AS "Date"
FROM "01-TryHackMe"
WHERE status = "✅ Done"
SORT date DESC
```

---

## 🔄 En cours

```dataview
LIST
FROM "01-TryHackMe"
WHERE status = "🔄 In Progress"
```

---

## 🛠️ Outils documentés

```dataview
TABLE file.mtime AS "Dernière modif"
FROM "03-Tools"
SORT file.name ASC
```

---

## 📅 Activité récente

```dataview
TABLE file.mtime AS "Modifié le"
FROM "01-TryHackMe" OR "04-Vulnerabilities"
SORT file.mtime DESC
LIMIT 10
```
