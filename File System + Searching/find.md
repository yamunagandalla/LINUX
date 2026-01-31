🔎 find Command — Complete Guide
📌 Purpose

find is used to search for files and directories based on:

Name

Type

Size

Time

Permissions

Owner

It can also perform actions on the results.

🧱 Basic Syntax
find [path] [options] [expression]

Part	Meaning
path	Where to search (e.g., /, /home)
options	Rules like name, size, type
expression	Action to perform (optional)
1️⃣ Search by Name
🔹 Exact Name
find /home -name "notes.txt"

🔹 Case-Insensitive Name
find /home -iname "notes.txt"

🔡 -name vs -iname

Linux file names are case-sensitive.

notes.txt   ≠   Notes.txt   ≠   NOTES.TXT


So the option you choose changes the result.

🧩 -name → Case-SENSITIVE search
find /home -name "notes.txt"


This will find only:

notes.txt


It will NOT find:

Notes.txt
NOTES.txt

🔎 -iname → Case-INSENSITIVE search
find /home -iname "notes.txt"


This will find:

notes.txt
Notes.txt
NOTES.TXT
NoTeS.TxT


Because i = ignore case

🌟 Using Wildcards
find /home -name "*.log"
find /var -name "config*"

🌟 Wildcards in find -name

Wildcards are pattern symbols that help you search when you don’t know the exact filename.

They work like search patterns instead of full names.

⭐ * (Star) → Matches ANY number of characters

Think of * as:
👉 “I don’t care what comes here”

Example 1
find /home -name "*.log"


Meaning:

Search for files that end with .log
* = anything before .log

Matches:

system.log
error.log
auth.log


Does NOT match:

log.txt
logfile

Example 2
find /var -name "config*"


Meaning:

File names that start with config
Anything can come after

Matches:

config
config.txt
config_backup
configuration.old

❓ ? (Question Mark) → Matches EXACTLY ONE character

Think:
👉 “There must be one character here, not zero, not many”

Example
find /home -name "file?.txt"


Matches:

file1.txt
fileA.txt
file9.txt


Does NOT match:

file10.txt  ❌ (two characters)  
file.txt    ❌ (no character)

🧠 Why Put Patterns in Quotes?

Always write like this:

find /home -name "*.txt"


If you don’t use quotes, the shell expands * before find runs, which can give wrong results.

🏠 House Analogy

You’re searching rooms for a box:

Pattern	Meaning in Real Life
*.log	“Any box that ends with LOG label”
config*	“Any box starting with CONFIG label”
file?.txt	“Box named file + one letter + .txt”
