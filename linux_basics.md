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

