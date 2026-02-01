# Combining Commands: grep | sort | uniq

This is a powerful command chain used to:

✅ Search
✅ Organize
✅ Remove duplicates

All in one line.

---

## 🧱 Basic Structure

```bash
grep "pattern" filename | sort | uniq
```

| Command | Job                           |
| ------- | ----------------------------- |
| grep    | Finds matching lines          |
| sort    | Arranges lines alphabetically |
| uniq    | Removes duplicate lines       |

---

## 🧠 How Data Flows

File → grep → matching lines → sort → ordered lines → uniq → unique lines

Each command processes the output of the previous one.

---

## 🔍 Step 1: grep — Filter the Data

`grep` searches for a word or pattern.

```bash
grep "error" log.txt
```

📤 Output → Only lines that contain "error"

---

## 🔤 Step 2: sort — Arrange the Data

`sort` puts lines in alphabetical (or numerical) order.

```bash
grep "error" log.txt | sort
```

Now all matching lines are grouped together, which helps `uniq` work properly.

---

## 🚫 Step 3: uniq — Remove Duplicates

`uniq` removes adjacent duplicate lines.

```bash
grep "error" log.txt | sort | uniq
```

📤 Output → Only one copy of each matching line

---

## ❗ Important Rule

🔴 `uniq` only removes duplicates that are next to each other

That’s why we use:

```bash
sort | uniq
```

instead of just:

```bash
uniq
```

---

## ✅ Example 1: Find Unique Error Messages

```bash
grep "error" log.txt | sort | uniq
```

✔ Searches all "error" lines
✔ Sorts them
✔ Removes repeated ones

📤 Final Output → List of unique error messages

---

## 🔢 Example 2: Count Unique Occurrences

Add `-c` to `uniq` to count duplicates:

```bash
grep "error" log.txt | sort | uniq -c
```

📤 Output:

```
3 Disk error
5 Network error
1 Login error
```

| Number | Meaning                          |
| ------ | -------------------------------- |
| 3      | "Disk error" appeared 3 times    |
| 5      | "Network error" appeared 5 times |

---

## 🏆 Example 3: Most Frequent Items

```bash
grep "error" log.txt | sort | uniq -c | sort -nr
```

| Part     | Meaning                                 |
| -------- | --------------------------------------- |
| uniq -c  | Count occurrences                       |
| sort -nr | Sort numbers in reverse (largest first) |

📤 Output → Most common errors at the top

---

## 🧪 Example 4: Unique Names from a File

```bash
cat students.txt | sort | uniq
```

Removes duplicate student names.

Better version (no need for `cat`):

```bash
sort students.txt | uniq
```

---

## ⚡ Real-World Uses

| Situation                  | Command                  |
| -------------------------- | ------------------------ |
| Unique IP addresses in log | `grep "192." access.log` |
| Unique usernames           | `cut -d' ' -f1 file.txt` |
| Count repeated words       | `tr ' ' '\n' < file.txt` |

---

## 🧠 Visual Analogy

Think of it like a factory line 🏭

1️⃣ grep → Picks only useful items
2️⃣ sort → Arranges them neatly
3️⃣ uniq → Throws away duplicates

---

## 🆚 Without vs With Sorting

❌ Wrong Order

```bash
grep "error" log.txt | uniq
```

Duplicates may remain because they aren’t together.

✅ Correct Order

```bash
grep "error" log.txt | sort | uniq
```

---

## 🎯 Summary

✔ grep filters
✔ sort organizes
✔ uniq removes duplicates
✔ Use `uniq -c` to count
✔ Use `sort -nr` after counting to find most frequent items
