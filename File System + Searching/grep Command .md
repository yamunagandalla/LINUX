# 🧠 grep Command

## 📌 What is grep?

grep is used to search for **text (words or patterns)** inside files.

It does **not** search file names — it searches **file content**.

---

## 🧱 Basic Syntax

```bash
grep "word" filename
```

**Example:**

```bash
grep "hello" file.txt
```

Shows lines in `file.txt` that contain `hello`.

---

## 📁 Search Inside a Folder

```bash
grep -r "word" foldername
```

`-r` = recursive → searches inside all files in that folder and subfolders.

**Example:**

```bash
grep -r "yamuna" ~/Desktop
```

---

## 🔡 Case Sensitivity

By default, `grep` is case-sensitive.

```bash
grep "yamuna" file.txt
```

**Matches:**

```
yamuna
```

**Does NOT match:**

```
YAMUNA
Yamuna
```

**Ignore case:**

```bash
grep -i "yamuna" file.txt
```

---

## ❌ Invert Match (Exclude a Word)

```bash
grep -v "word" file.txt
```

Shows lines that do **NOT** contain the word.

Combine with ignore case:

```bash
grep -vi "yamuna" file.txt
```

---

## 🔢 Show Line Numbers

```bash
grep -n "word" file.txt
```

Output format:

```
line_number:line_content
```

---

## 📄 Show Only File Names (Not Lines)

```bash
grep -rl "word" folder
```

Useful to find which files contain a word.

---

## 🎯 Match Whole Word Only

```bash
grep -w "root" file.txt
```

**Matches:**

```
root
```

**Does NOT match:**

```
rootuser
myrootpass
```

---

## 🌈 Highlight Matches

```bash
grep --color=auto "word" file.txt
```

---

## 🔍 Search Multiple Files

```bash
grep "error" *.log
```

Searches all `.log` files in current directory.

---

## 🤝 Combine with find

```bash
find /etc -name "*.conf" -exec grep "password" {} \;
```

Step 1 → Find config files

Step 2 → Search inside them

---

## 🚫 Hide Permission Errors

```bash
grep -r "word" /etc 2>/dev/null
```

---

## ⚡ Most Important Options

| Option | Meaning                    |
| ------ | -------------------------- |
| `-r`   | Search folders recursively |
| `-i`   | Ignore case                |
| `-v`   | Show non-matching lines    |
| `-n`   | Show line numbers          |
| `-l`   | Show only file names       |
| `-w`   | Match whole word           |

---

## 🧠 Difference Between find and grep

| Command | Purpose                        |
| ------- | ------------------------------ |
| `find`  | Searches for file names        |
| `grep`  | Searches for text inside files |

---

## 🧪 Practice Commands

```bash
grep "root" /etc/passwd
grep -i "bash" /etc/passwd
grep -v "nologin" /etc/passwd
grep -r "password" ~/Desktop
grep -ril "yamuna" ~/Desktop
```
