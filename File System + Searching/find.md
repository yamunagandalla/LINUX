# 🔎 find Command — Complete Guide

## 📌 Purpose

The `find` command is used to search for files and directories based on:

- Name  
- Type  
- Size  
- Time  
- Permissions  
- Owner  

It can also perform actions on the search results.

---

## 🧱 Basic Syntax

```bash
find [path] [options] [expression]
Part	Meaning
path	Where to search (e.g., /, /home)
options	Rules like name, size, type
expression	Action to perform (optional)

1️⃣ Search by Name
🔹 Exact Name
bash
Copy code
find /home -name "notes.txt"
🔹 Case-Insensitive Name
bash
Copy code
find /home -iname "notes.txt"
🔡 -name vs -iname
Linux file names are case-sensitive.

Copy code
notes.txt   ≠   Notes.txt   ≠   NOTES.TXT
So the option you choose changes the result.

🧩 -name → Case-SENSITIVE Search
bash
Copy code
find /home -name "notes.txt"
✔ Finds:

Copy code
notes.txt
❌ Does NOT find:

Copy code
Notes.txt
NOTES.txt
🔎 -iname → Case-INSENSITIVE Search
bash
Copy code
find /home -iname "notes.txt"
✔ Finds:

Copy code
notes.txt
Notes.txt
NOTES.TXT
NoTeS.TxT
Because i = ignore case

🌟 Using Wildcards
bash
Copy code
find /home -name "*.log"
find /var -name "config*"
🌟 Wildcards in find -name
Wildcards help when you don’t know the exact filename.

They act as search patterns.

⭐ * (Star) → Matches ANY number of characters
Think of * as:
“I don’t care what comes here”

Example 1
bash
Copy code
find /home -name "*.log"
Meaning: Files ending with .log

✔ Matches:

lua
Copy code
system.log
error.log
auth.log
❌ Does NOT match:

lua
Copy code
log.txt
logfile
Example 2
bash
Copy code
find /var -name "config*"
Meaning: File names starting with config

✔ Matches:

arduino
Copy code
config
config.txt
config_backup
configuration.old
❓ ? (Question Mark) → Matches EXACTLY ONE character
Think:
“There must be one character here”

Example
bash
Copy code
find /home -name "file?.txt"
✔ Matches:

Copy code
file1.txt
fileA.txt
file9.txt
❌ Does NOT match:

csharp
Copy code
file10.txt
file.txt
🧠 Why Put Patterns in Quotes?
Always write:

bash
Copy code
find /home -name "*.txt"
Without quotes, the shell expands * before find runs, which can give incorrect results.

🏠 House Analogy
Pattern	Meaning in Real Life
*.log	Any box that ends with a LOG label
config*	Any box starting with a CONFIG label
file?.txt	A box named file + one letter + .txt
