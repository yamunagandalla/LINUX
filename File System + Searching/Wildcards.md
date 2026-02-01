# Wildcards (*, ?, [ ])

Wildcards are special symbols used to match file names when you don’t know the exact name.

They are expanded by the shell (bash) before the command runs.

---

## ⭐ `*` — Match ANY number of characters

Matches zero or more characters

```bash
ls *.txt
```

### Matches:

```
file.txt
notes.txt
a.txt
```

### Does NOT match:

```
file.pdf
txtfile
```

### Beginning pattern

```bash
ls log*
```

Matches:

```
log
log1
logfile
logs.txt
```

### Middle pattern

```bash
ls file*.txt
```

Matches:

```
file.txt
file1.txt
file_backup.txt
```

---

## ❓ `?` — Match EXACTLY ONE character

```bash
ls file?.txt
```

### Matches:

```
file1.txt
fileA.txt
file9.txt
```

### Does NOT match:

```
file10.txt ❌ (two characters)
file.txt   ❌ (zero characters)
```

---

## `[ ]` — Match a Set or Range of Characters

### Match specific characters

```bash
ls file[123].txt
```

Matches:

```
file1.txt
file2.txt
file3.txt
```

### Match a range

```bash
ls file[a-z].txt
```

Matches any lowercase letter in that position.

```bash
ls file[0-9].txt
```

Matches any single digit.

---

## 🔄 Combine Wildcards

```bash
ls *[0-9].pdf
```

Files ending with a number before `.pdf`

---

## Important Difference

| Wildcards           | grep Patterns                    |
| ------------------- | -------------------------------- |
| Used for file names | Used for text search             |
| Handled by shell    | Handled by grep                  |
| Example: `ls *.txt` | Example: `grep "hello" file.txt` |

So:

```bash
ls *.txt        ✅ correct
grep "*.txt"    ❌ searches for literal text *.txt
```

---

## 💻 Works with Many Commands

```bash
cp *.txt backup/
rm file?.log
mv *.pdf Documents/
```

---

## 🧠 Memory Trick

| Symbol | Meaning       |
| ------ | ------------- |
| *      | Anything      |
| ?      | One character |
| [abc]  | One from set  |
| [a-z]  | Range         |

---

## Practice

```bash
ls *.txt
ls file?.txt
ls *[0-9].pdf
```
