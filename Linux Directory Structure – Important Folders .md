🐧 Linux Directory Structure – Important Folders

Linux is organized like a well-planned house 🏠
Each directory has a specific purpose. Understanding this is very important for Linux, Servers, and Cybersecurity.

📁 /etc — System Configuration Files

This folder contains all system settings and configuration files.

If Linux were a mobile phone, /etc would be the Settings app ⚙️

🔹 What is stored here?

User account information → /etc/passwd

Encrypted passwords → /etc/shadow

Network configuration files

Service configurations (SSH, Apache, MySQL, etc.)

🔹 Example

SSH server settings:

/etc/ssh/sshd_config

✅ In Short

/etc = All system configuration files

📁 /var — Variable Data Files

The word var means variable.
This directory stores data that keeps changing while the system runs.

🔹 What is stored here?

System logs → /var/log

Emails → /var/mail

Website files → /var/www

Cache files → /var/cache

Databases → /var/lib

🔹 Example

System logs:

/var/log/syslog

✅ In Short

/var = Data that grows or changes (logs, mail, databases)

📁 /bin — Essential User Commands

“bin” stands for binaries (program files).

This directory contains basic commands needed for the system to function, even in recovery mode.

🔹 Common commands found here

ls → List files

cp → Copy files

mv → Move files

cat → Display file content

mkdir → Create directory

🔹 Try this command
ls /bin

✅ In Short

/bin = Essential survival commands in Linux

📁 /opt — Optional Software Packages

“opt” means optional.

This folder is used to install third-party or additional software that is not part of the default Linux system.

🔹 Examples

Google Chrome → /opt/google/

Zoom → /opt/zoom/

Custom company software

This keeps extra applications separate from core system files.

✅ In Short

/opt = Optional or third-party software installations

📁 /home — Users’ Personal Folders

This directory contains home folders for all normal users.

Each user gets their own private space to store files.

🔹 Example

If the username is teja, the home folder will be:

/home/teja


Inside it, you store:

Documents

Downloads

Pictures

Projects

Code files

✅ In Short

/home = Personal folders of normal users

📁 /root — Superuser’s Home Folder

This is the home directory of the root user (system administrator).

⚠️ It is not inside /home

🔹 Who is root?

The root user has full control over the system — can install software, change settings, manage users, etc.

🔹 Root’s home directory:
/root

✅ In Short

/root = Home folder of the administrator (root user)

📁 /usr — User Programs & Applications

Despite the name, /usr does not mean user personal files.
It stands for Unix System Resources.

This directory contains most installed software, libraries, and commands.

🔹 Important subfolders
Folder	Purpose
/usr/bin	Most user commands (like python, nano, gcc)
/usr/sbin	System admin commands
/usr/lib	Libraries required by programs
/usr/share	Shared files like manuals and documentation
🔹 Example

Python command location:

/usr/bin/python3

✅ In Short

/usr = Installed programs and application files

🧠 Quick Memory Table
Directory	Purpose	Easy Way to Remember
/etc	Configuration files	Edit The Config
/var	Changing data	Data that varies
/bin	Basic commands	Bin = binaries
/opt	Optional software	Optional programs
/home	User personal folders	Users live here
/root	Admin’s home folder	Root user’s house
/usr	Programs & libraries	Unix System Resources
