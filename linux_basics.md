# Linux Basic Commands

## 1. ls – List Files and Directories
**Purpose:** Shows the files and folders in the current directory.  

**Common Options:**  
- `ls` → list visible files  
- `ls -a` → list all files including hidden (.files)  
- `ls -l` → detailed list (permissions, owner, size, time)  
- `ls -la` → detailed + hidden files  

**Example:**  
```bash
ls
ls -a
ls -la


Use in Cybersecurity:
Check what files exist, find hidden files, inspect directories on a compromised system.

File Details:

File type and permissions (-rw-r--r--, drwxr-xr-x, lrwxrwxrwx)

First character = file type: - regular, d directory, l symbolic link, c character device, b block device, p FIFO, s socket

Next 9 characters = permissions (owner/group/others): r read, w write, x execute

Special letters: s/S = SUID/SGID, t/T = sticky bit (common on /tmp)

Hard link count (number of directory entries pointing to the inode)

Owner (user)

Group

Size (3.2K, 160 bytes) – use -h for human-readable

Timestamp – shows modification time (mtime) by default

Filename – if symbolic link (l), shows -> target

2. pwd – Print Working Directory

Purpose: Shows your current location in Linux.

Example:

pwd


Output Example:

/home/isha/Documents


Use in Cybersecurity:
Helps track location during enumeration, privilege escalation, or file-system navigation.

3. cd – Change Directory

Purpose: Move from one folder to another.

Common Uses:

cd foldername        # go inside a folder
cd ..                # go back one level
cd /path/to/folder   # go to a specific path
cd ~                 # go to home directory
cd /                 # go to root directory


Use in Cybersecurity:
Navigate directories in a target machine, find configs/logs/password files, etc.

4. clear – Clear the Terminal

Purpose: Removes all previous terminal output for a clean view.

Example:

clear


Shortcut: Ctrl + L

Use in Cybersecurity:
Keeps your terminal organized while running multiple commands.

5. history – Show Previously Used Commands

Purpose: Displays your past commands with numbers.

Example:

history


Rerun a command:

!37   # runs command number 37


Clear history:

history -c


Use in Cybersecurity:

View what commands were executed

Helps track mistakes

Attackers often delete history to hide traces

6. mkdir — Make Directory

Purpose: Creates a new folder.

Usage:

mkdir foldername          # create single folder
mkdir -p parent/child     # create nested folders

7. rmdir — Remove Directory

Purpose: Deletes an empty folder.

Usage:

rmdir foldername


⚠️ Does not work if files are inside.

8. touch — Create File

Purpose: Creates an empty file or updates its timestamp.

Usage:

touch file.txt           # create file
touch .secret.txt        # create hidden file

9. cp — Copy Files and Folders

Purpose: Copies files or directories.

Usage:

cp file1.txt file2.txt          # copy file
cp -r folder1 folder2           # copy folder recursively

10. mv — Move or Rename

Purpose: Moves or renames files/folders.

Usage:

mv old.txt new.txt                  # rename a file
mv file.txt /path/to/folder         # move file to another directory

11. rm — Remove Files and Directories

Purpose: Deletes files and folders permanently.

Usage:

rm file.txt               # delete file
rm -r foldername          # delete folder with all contents
rm -rf foldername         # force delete (dangerous)

12. Navigation Commands
cd ..       # go back one folder
cd ~        # go home
cd /        # go to root
pwd         # check current location

1️⃣ cat – Concatenate and display files

Shows whole file content at once.

Good for small files.

Example:

cat file.txt


Output: Prints all lines of file.txt to terminal.

2️⃣ less – Scrollable viewer (forward & backward)

Lets you scroll page by page and search inside file.

Handles large files efficiently.

Navigation inside less:

Space → next page

b → previous page

/word → search for word

q → quit

Example:

less file.txt

3️⃣ more – Scrollable viewer (forward only)

Shows file page by page, but cannot scroll back.

Simpler than less.

Navigation inside more:

Space → next page

Enter → next line

q → quit

Example:

more file.txt

4️⃣ head – View first lines of a file

Default: shows first 10 lines.

Can specify number of lines with -n.

Example:

head file.txt           # first 10 lines
head -n 5 file.txt      # first 5 lines

5️⃣ tail – View last lines of a file

Default: shows last 10 lines.

Can specify number of lines with -n.

Very useful for logs.

Example:

tail file.txt           # last 10 lines
tail -n 5 file.txt      # last 5 lines
tail -f file.txt        # live updates as file grows (log monitoring)


✅ Summary Table

Command	Shows	Notes
cat	Whole file	Best for small files
less	Page by page	Scroll forward/back, search inside
more	Page by page	Scroll forward only
head	First lines	Default 10 lines, use -n for custom
tail	Last lines	Default 10 lines, use -n or -f for live updates
