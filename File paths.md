# Linux File Paths – Absolute & Relative

## 🌟 1. What is a File Path?
A **file path** is the address of a file or folder in your Linux system.  
It tells the system *exactly where* the file is located.

---

## 🌍 2. Absolute Path
An **absolute path** always starts from the **root directory `/`**.

💡 It gives the *complete* address of a file from the top of the Linux file system.

### **Examples**
/home/rgukt/Desktop/mine.txt
/etc/passwd

markdown
Copy code

### **Key Points**
- ✔️ Always starts with `/`
- ✔️ Works from anywhere in the system  
- ✔️ Very accurate and never changes  
- ✔️ Recommended for scripts and automation

---

## 🚶‍♀️ 3. Relative Path
A **relative path** is written from your **current working directory**, not from `/`.

💡 It depends on where you are standing (your current location).

### **Examples**
If you are in:
/home/rgukt/

makefile
Copy code

Then:
Desktop/mine.txt → relative path

arduino
Copy code

If you are inside `/home/rgukt/Desktop`:
../Documents/notes.txt → go one step back, then go to Documents

yaml
Copy code

### **Key Points**
- ❌ Does not start with `/`
- ✔️ Depends on current directory  
- ✔️ Shorter and faster to type  
- Uses special symbols:
  - `.` → current directory  
  - `..` → parent directory (one step back)

---

## 🔍 4. Absolute vs Relative (Quick Table)

| Feature | Absolute Path | Relative Path |
|---------|---------------|---------------|
| Starts with `/` | ✔️ Yes | ❌ No |
| From root directory | ✔️ Yes | ❌ No |
| Depends on current directory | ❌ No | ✔️ Yes |
| Example | `/home/isha/file.txt` | `Documents/file.txt` |
| More reliable | ✔️ Yes | ❌ No |
| Shorter to type | ❌ No | ✔️ Yes |

---

## 🧠 5. Mini Examples to Understand Clearly

### **Example 1**
You're in:
/home/isha/

bash
Copy code

Relative path:
```bash
cat Desktop/mine.txt
Absolute path:

bash
Copy code
cat /home/isha/Desktop/mine.txt
Example 2
Move one folder back:

bash
Copy code
cd ..
Enter a folder using relative path:

bash
Copy code
cd Project
Enter a folder using absolute path:

bash
Copy code
cd /home/isha/Project
✔️ Summary
Absolute path = full address starting with /.

Relative path = short address based on where you currently are.

Linux uses both — you will switch between them all the time.
