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

## 🏠 House Analogy

| Pattern     | Meaning in Real Life                 |
| ----------- | ------------------------------------ |
| `*.log`     | Any box that ends with a LOG label   |
| `config*`   | Any box starting with a CONFIG label |
| `file?.txt` | A box named file + one letter + .txt |

---

## 2️⃣ Search by Type

| Type | Meaning       |
| ---- | ------------- |
| f    | Regular file  |
| d    | Directory     |
| l    | Symbolic link |

```bash
find /home -type f -name "*.txt"
find /etc -type d
```

---

## 3️⃣ Search by Size

| Format    | Meaning      |
| --------- | ------------ |
| +         | Greater than |
| -         | Less than    |
| No symbol | Exact size   |

| Unit | Meaning   |
| ---- | --------- |
| k    | Kilobytes |
| M    | Megabytes |
| G    | Gigabytes |

```bash
find /home -size +10M
find /var -size -500k
find / -size 100M
```

---

## 4️⃣ Search by Time

**Modified time (content changed)**

```bash
find /home -mtime -2   # Modified in last 2 days
find /home -mtime +7   # Modified more than 7 days ago
```

**Access time (last opened)**

```bash
find /home -atime -1
```

**Change time (permissions/owner changed)**

```bash
find /home -ctime -3
```

---

## 5️⃣ Search by Permissions

```bash
find / -perm 777
```

Find files with full permissions (dangerous in security)

```bash
find /home -perm -u=r
```

Files readable by owner

---

## 6️⃣ Search by Owner or Group

```bash
find /home -user isha
find /var -group www-data
```

---

## 7️⃣ Combining Conditions

Use `-and`, `-or`

```bash
find /home -type f -name "*.txt" -size +1M
```

Find text files larger than 1MB

```bash
find /home -name "*.txt" -or -name "*.pdf"
```

---

## 8️⃣ Execute Actions on Results

**Delete files**

```bash
find /home -name "*.tmp" -delete
```

**Run a command on each file**

```bash
find /home -name "*.txt" -exec cat {} \;
```

**Change permissions**

```bash
find /home -name "*.sh" -exec chmod +x {} \;
```

---

## 9️⃣ Ignore Permission Errors

```bash
find / -name "shadow" 2>/dev/null
```

`2>/dev/null` hides error messages

---

## 🔟 Limit Search Depth

```bash
find /home -maxdepth 1 -name "*.txt"
```

Search only current directory, not subfolders

---

## 🧠 Real-World Cybersecurity Uses

| Task                         | Command Example                  |
| ---------------------------- | -------------------------------- |
| Find SUID files              | `find / -perm -4000 2>/dev/null` |
| Find world-writable files    | `find / -perm -002 2>/dev/null`  |
| Find log files               | `find /var/log -name "*.log"`    |
| Find recently modified files | `find / -mtime -1 2>/dev/null`   |

---

## ⚠️ Important Notes

* Searching from `/` can be slow
* Use `sudo` if you need full access
* Be careful with `-delete`

---

## 🧪 Practice Commands

Try these safely:

```bash
find /home -type f -name "*.txt"
find /var/log -name "*.log"
find /home -size +1M
```
