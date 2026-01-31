# 🔎 find Command — Complete Guide

## 📌 Purpose

The `find` command is used to search for files and directories based on:

* Name
* Type
* Size
* Time
* Permissions
* Owner

It can also perform actions on the search results.

---

## 🧱 Basic Syntax

```bash
find [path] [options] [expression]
```

| Part       | Meaning                              |
| ---------- | ------------------------------------ |
| path       | Where to search (e.g., `/`, `/home`) |
| options    | Rules like name, size, type          |
| expression | Action to perform (optional)         |

---

## 1️⃣ Search by Name

### 🔹 Exact Name

```bash
find /home -name "notes.txt"
```

### 🔹 Case-Insensitive Name

```bash
find /home -iname "notes.txt"
```

---

## 🔡 `-name` vs `-iname`

Linux file names are **case-sensitive**.

```
notes.txt   ≠   Notes.txt   ≠   NOTES.TXT
```

So the option you choose changes the result.

### 🧩 `-name` → Case-SENSITIVE Search

```bash
find /home -name "notes.txt"
```

✔ Finds:

```
notes.txt
```

❌ Does NOT find:

```
Notes.txt
NOTES.txt
```

---

### 🔎 `-iname` → Case-INSENSITIVE Search

```bash
find /home -iname "notes.txt"
```

✔ Finds:

```
notes.txt
Notes.txt
NOTES.TXT
NoTeS.TxT
```

Because **i = ignore case**

---

## 🌟 Using Wildcards

```bash
find /home -name "*.log"
find /var -name "config*"
```

### 🌟 Wildcards in `find -name`

Wildcards help when you don’t know the exact filename.

They act as **search patterns**.

---

### ⭐ `*` (Star) → Matches ANY number of characters

Think of `*` as:
**“I don’t care what comes here”**

#### Example 1

```bash
find /home -name "*.log"
```

Meaning: Files ending with `.log`

✔ Matches:

```
system.log
error.log
auth.log
```

❌ Does NOT match:

```
log.txt
logfile
```

---

#### Example 2

```bash
find /var -name "config*"
```

Meaning: File names starting with `config`

✔ Matches:

```
config
config.txt
config_backup
configuration.old
```

---

### ❓ `?` (Question Mark) → Matches EXACTLY ONE character

Think:
**“There must be one character here”**

#### Example

```bash
find /home -name "file?.txt"
```

✔ Matches:

```
file1.txt
fileA.txt
file9.txt
```

❌ Does NOT match:

```
file10.txt
file.txt
```

---

## 🧠 Why Put Patterns in Quotes?

Always write:

```bash
find /home -name "*.txt"
```

Without quotes, the **shell expands `*` before `find` runs**, which can give incorrect results.

---
