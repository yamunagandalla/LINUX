# 🧠 Pipes and Redirection in Linux

These features allow commands to work together and control where input and output go.

---

## 🔗 1️⃣ Pipes (`|`)

A **pipe** sends the output of one command to the input of another command.

### 📌 Syntax

```bash
command1 | command2
```

**Meaning:**
➡ Output of `command1` becomes input for `command2`

### ✅ Examples

```bash
ls | grep ".txt"
```

List files → filter only `.txt`

```bash
ps aux | grep firefox
```

Show running processes → search for Firefox

```bash
cat file.txt | sort
```

Show file contents → sort them alphabetically

### 🧠 Why Pipes Are Powerful

Instead of doing everything manually, you can chain commands to process data step by step.

---

## 📤 2️⃣ Output Redirection (`>`)

Saves the output of a command into a file.

```bash
command > file
```

⚠ If the file exists, it will be **overwritten**.

### Example

```bash
ls > list.txt
```

Saves file list into `list.txt`

---

## ➕ 3️⃣ Append Output (`>>`)

Adds output to the end of a file without deleting old content.

```bash
command >> file
```

### Example

```bash
date >> log.txt
```

Adds the current date to the log file

---

## 📥 4️⃣ Input Redirection (`<`)

Takes input for a command from a file instead of the the keyboard.

```bash
command < file
```

### Example

```bash
sort < names.txt
```

Sorts the contents of `names.txt`

---

## 🔀 Combining Pipes and Redirection

```bash
ls | grep ".txt" > textfiles.txt
```

Step 1 → List files
Step 2 → Filter `.txt` files
Step 3 → Save result to file

---

## 🔥 Real Usage Examples

### Count lines containing a word

```bash
grep "error" log.txt | wc -l
```

### Save users with bash shell

```bash
grep "/bin/bash" /etc/passwd > bash_users.txt
```

### Sort and remove duplicates

```bash
cat names.txt | sort | uniq
```

---

## 🧠 Summary Table

| Symbol | Purpose                 |                                       |
| ------ | ----------------------- | ------------------------------------- |
| `      | `                       | Send output of one command to another |
| `>`    | Save output (overwrite) |                                       |
| `>>`   | Save output (append)    |                                       |
| `<`    | Take input from a file  |                                       |

---

## 🎯 Key Idea

Linux commands are like building blocks.
Pipes and redirection let you connect those blocks to build powerful workflows.
