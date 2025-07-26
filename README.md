# Comprehensive Linux Ubuntu Command Reference

This is a complete guide of essential Linux (Ubuntu) command-line utilities, categorized by topic, with command syntax and one-line explanations. At the end, you'll find a classification of Linux functionality areas.

---
## 📑 Table of Contents
- [1. Introduction to Shell](#1-introduction-to-shell)
- [2. Shell Types](#2-shell-types)
- [3. Bash Shell Functions](#3-bash-shell-functions)
- [4. Getting Help in Shell](#4-getting-help-in-shell)
- [5. File and Directory Management](#5-file-and-directory-management)
- [6. Core Linux System](#6-core-linux-system)
- [7. Linux Kernel](#7-linux-kernel)
- [8. User and Permissions Management](#8-user-and-permissions-management)
- [9. Sudo and Root Access](#9-sudo-and-root-access)
- [10. Run Levels / Systemd Targets](#10-run-levels--systemd-targets)
- [11. File Types and Metadata](#11-file-types-and-metadata)
- [12. Package Management](#12-package-management)
  - [RPM (RHEL-based)](#rpm-rhel-based)
  - [YUM (CentOS/RHEL)](#yum-centosrhel)
  - [DPKG (Debian/Ubuntu)](#dpkg-debianubuntu)
  - [APT / APT-GET (Ubuntu/Debian)](#apt--apt-get-ubuntudebian)
- [13. Shell Scripting Basics](#13-shell-scripting-basics)
- [14. Compression and Archiving](#14-compression-and-archiving)
- [15. File Searching and Filtering](#15-file-searching-and-filtering)
- [16. Text Editors – VIM](#16-text-editors--vim)
- [17. Networking and DNS](#17-networking-and-dns)
- [18. System Monitoring and Troubleshooting](#18-system-monitoring-and-troubleshooting)
- [19. Task Automation and Scheduling](#19-task-automation-and-scheduling)
- [20. Disk and Partition Management](#20-disk-and-partition-management)
- [21. Firewall and Security Tools](#21-firewall-and-security-tools)
- [22. Environment Variables](#22-environment-variables)
- [23. Additional Useful Commands](#23-additional-useful-commands)
- [🧩 Linux Functional Categories Summary](#-linux-functional-categories-summary)
----
## 1. Introduction to Shell
> Theory: The shell is a command-line interpreter that allows users to communicate with the Linux operating system. It reads user input, interprets it as commands, and passes them to the OS. It also supports scripting for automating repetitive tasks.

* `echo "Hello World"` – Prints text to terminal.
* `whoami` – Displays current username.
* `pwd` – Shows current working directory.
* `clear` – Clears the terminal screen.
* `exit` – Exits the shell.

## 2. Shell Types
> Theory: Linux supports multiple types of shells, each with its own syntax and features. Common shells include:
> - sh – Original Bourne Shell
> - bash – Bourne Again Shell (default in Ubuntu)
> - zsh – Advanced shell with scripting features
> - ksh – Korn shell
> - csh – C Shell

You can change or list available shells as needed.
* `echo $SHELL` – Displays the current shell.
* `chsh -s /bin/bash` – Changes the login shell to Bash.
* `cat /etc/shells` – Lists available shells.

## 3. Bash Shell Functions
> Theory: Functions in Bash are blocks of code that can be defined and reused throughout a shell session or script. They help modularize logic, accept parameters, and reduce redundancy in scripts.

* `function greet() { echo "Hello $1"; }` – Defines a Bash function.
* `greet Arya` – Calls the `greet` function with argument.
* `declare -f` – Lists all defined functions.

## 4. Getting Help in Shell
> Theory: Linux offers several help utilities:
> - "man pages (manual)"
> - --help flags
> - whatis, apropos, and online resources

These tools help you understand commands, flags, and usage quickly.
* `man ls` – Opens manual page for `ls` command.
* `ls --help` – Displays help for `ls` command.
* `whatis ls` – Gives a one-line description.
* `apropos list` – Searches man pages for related commands.

## 5. File and Directory Management
> Theory: File management includes creating, moving, copying, and deleting files or directories. Understanding how Linux handles files and paths is essential for navigation, automation, and organization of data.

* `touch file.txt` – Creates an empty file.
* `mkdir folder` – Creates a directory.
* `rm file.txt` – Deletes a file.
* `rm -r folder` – Deletes a directory recursively.
* `cp file1.txt file2.txt` – Copies a file.
* `mv file1.txt file2.txt` – Renames or moves a file.
* `cat > file.txt` – Writes input to file (overwrite).
* `echo "Text" >> file.txt` – Appends text to file.

## 6. Core Linux System
> Theory: These commands provide an overview of your system’s kernel, architecture, uptime, resource usage, and running tasks. It’s useful for monitoring, auditing, and diagnosing issues.

* `uname -a` – Displays system information.
* `top` – Displays active processes.
* `df -h` – Shows disk usage.
* `free -m` – Displays memory usage.

## 7. Linux Kernel
> Theory: The kernel is the core of the operating system, responsible for hardware management, process control, and system calls. Knowing your kernel version helps determine compatibility with modules, drivers, and packages.

* `uname -r` – Displays the kernel version.
* `cat /proc/version` – Shows detailed kernel version info.

## 8. User and Permissions Management
> Theory: Linux is a multi-user OS. It supports user creation, group assignment, and permission controls (read, write, execute) to ensure system security and controlled access to files and directories.

* `chmod 755 file.txt` – Sets permissions.
* `chown user:group file.txt` – Changes ownership.
* `ls -l` – Lists file permissions.
* `umask` – Shows default permission mask.
* `passwd` – Changes user password.
* `who` – Lists logged in users.
* `adduser username` – Adds a new user.
* `deluser username` – Deletes a user.
* `usermod -aG group username` – Adds user to a group.
* `groupadd groupname` – Adds a new group.

## 9. Sudo and Root Access
> Theory: sudo grants administrative (root) privileges temporarily for command execution. It's safer than logging in as root and helps protect the system from accidental misconfigurations.

* `sudo command` – Runs command with superuser privileges.
* `sudo su` – Switches to root user.

## 10. Run Levels / Systemd Targets
> Theory: Runlevels (in traditional SysV) or systemd targets (in modern distros) define the system's operational state—like multi-user mode, graphical mode, or maintenance mode. systemctl is used to manage these states in Ubuntu.

* `runlevel` – Shows the current run level.
* `systemctl get-default` – Shows default systemd target.
* `systemctl set-default multi-user.target` – Sets CLI runlevel.
* `systemctl isolate graphical.target` – Switches to GUI mode.

## 11. File Types and Metadata
> Theory: Every file in Linux has metadata including permissions, size, timestamps, and type (regular file, directory, symlink, etc.). Understanding file types helps when writing scripts, managing backups, or securing systems.

* `ls -l` – Lists file details including type.
* `file filename` – Displays file type.

## 12. Package Management
> Theory: Package managers help install, update, and remove software:
> - RPM: Used in RHEL, CentOS
> - YUM: High-level frontend to RPM
> - DPKG: Debian package manager (low-level)
> - APT / APT-GET: Advanced package management on Debian/Ubuntu systems

### RPM (RHEL-based)

* `rpm -ivh package.rpm` – Installs an RPM package.
* `rpm -qa` – Lists installed RPM packages.

### YUM (CentOS/RHEL)

* `yum install package` – Installs package.
* `yum remove package` – Removes package.

### DPKG (Debian/Ubuntu)

* `dpkg -i package.deb` – Installs `.deb` package.
* `dpkg -l` – Lists installed packages.

### APT / APT-GET (Ubuntu/Debian)

* `sudo apt update` – Updates package list.
* `sudo apt upgrade` – Upgrades packages.
* `sudo apt install package` – Installs package.
* `sudo apt remove package` – Removes package.

## 13. Shell Scripting Basics
> Theory: Shell scripting allows task automation by combining commands, logic, loops, and variables. It’s widely used for writing cron jobs, provisioning, deployment, and administrative tasks.

* `for i in {1..5}; do echo $i; done` – Loop in shell.
* `if [ -f file.txt ]; then echo "Exists"; fi` – Conditional in shell.
* `while true; do echo hello; sleep 1; done` – Infinite loop example.

## 14. Compression and Archiving
> Theory: Archiving groups multiple files; compression reduces file size. tar, gzip, and zip are commonly used for backups, transfers, and installations.

* `tar -cvf archive.tar file1 file2` – Creates a tar archive.
* `tar -xvf archive.tar` – Extracts a tar archive.
* `gzip file.txt` – Compresses a file.
* `gunzip file.txt.gz` – Decompresses a gzip file.
* `zip file.zip file1 file2` – Creates a zip archive.
* `unzip file.zip` – Extracts a zip archive.

## 15. File Searching and Filtering
> Theory: Tools like grep, find, and locate help you search files by content or name. Mastering them saves time and improves productivity when navigating large file systems.

* `grep "text" file.txt` – Searches for text in file.
* `find . -name file.txt` – Finds file by name.
* `locate filename` – Quickly finds files by name (uses DB).

## 16. Text Editors – VIM
> Theory: VIM is a powerful terminal-based text editor. It supports syntax highlighting, macros, and scripting. Understanding modes (insert, normal, visual, command) is crucial for efficient use.

* `vim file.txt` – Opens file in VIM.
* `i` – Insert mode.
* `Esc + :w` – Save file.
* `Esc + :q` – Quit.
* `Esc + :wq` – Save and quit.

## 17. Networking and DNS
> Theory: Linux provides networking tools to manage IPs, check connectivity, and troubleshoot issues. Tools like ping, ip, netstat, dig, and nslookup are essential for system admins and DevOps engineers.

* `ping google.com` – Checks connectivity.
* `ifconfig` – Displays network interfaces.
* `ip a` – Shows IP addresses.
* `nslookup domain.com` – DNS query.
* `dig domain.com` – Detailed DNS info.
* `netstat -tulpn` – Shows ports and listening services.
* `traceroute google.com` – Shows network hops.
* `curl -I https://example.com` – Fetches HTTP headers.
* `wget http://example.com/file` – Downloads a file.

## 18. System Monitoring and Troubleshooting
> Theory: Monitoring tools (top, ps, uptime, journalctl) help assess system health, load, and running processes. Logs and kernel messages (dmesg) provide insights during troubleshooting.

* `dmesg` – Kernel logs.
* `journalctl` – Systemd logs.
* `systemctl status service` – Status of service.
* `tail -f /var/log/syslog` – Real-time log output.
* `uptime` – Shows system uptime.
* `top` – Displays running processes.
* `ps aux` – Lists all running processes.
* `kill PID` – Kills a process by PID.
* `killall processname` – Kills all processes by name.
* `nice -n 10 command` – Sets priority of a process.
* `renice PID` – Changes priority of a running process.

## 19. Task Automation and Scheduling
> Theory: Linux automates tasks using:
> - cron – For repeated jobs (hourly, daily)
> - at – For one-time tasks
> Scheduled jobs improve efficiency and ensure timely execution of backups, updates, and monitoring tasks.

* `crontab -e` – Edits scheduled jobs.
* `at now + 5 minutes` – Schedules a one-time task.

## 20. Disk and Partition Management
> Theory: Commands like lsblk, mount, umount, and fdisk help manage storage devices, partitions, and mounting points. Proper disk management is crucial for storage optimization and system stability.

* `lsblk` – Lists block devices.
* `fdisk -l` – Displays disk partition table.
* `mount /dev/sda1 /mnt` – Mounts partition.
* `umount /mnt` – Unmounts partition.

## 21. Firewall and Security Tools
> Theory: Linux security is enforced using tools like:
> - UFW: Simple firewall wrapper over iptables
> - iptables: Advanced firewall rules manager
> These tools control access to network services and protect systems from unauthorized access.

* `ufw enable` – Enables uncomplicated firewall.
* `ufw allow 22` – Allows SSH traffic.
* `ufw status` – Displays firewall status.
* `iptables -L` – Lists current iptables rules.

## 22. Environment Variables
> Theory: Environment variables define system-wide or session-specific configurations. Variables like PATH, HOME, and USER are essential for running applications and scripts consistently.

* `export VAR=value` – Sets a variable for session.
* `echo $VAR` – Displays value of a variable.
* `printenv` – Prints environment variables.
* `source ~/.bashrc` – Reloads bash config.

## 23. Additional Useful Commands
> Theory: Utility commands like alias, hostname, and history enhance your workflow by simplifying tasks and understanding system behavior. These are helpful for customization and productivity.

* `history` – Shows command history.
* `alias ll='ls -la'` – Creates alias.
* `hostname` – Displays hostname.

---

## 🧩 Linux Functional Categories Summary

| Category                  | Description                                 |
| ------------------------- | ------------------------------------------- |
| Shell Basics              | Starting shell, types, help, basic commands |
| Shell Scripting           | Functions, loops, conditionals              |
| Files and Directories     | Creating, deleting, moving, modifying files |
| System Info & Resources   | System, memory, CPU, kernel                 |
| Package Management        | RPM, YUM, DPKG, APT tools                   |
| User & Permission Mgmt    | Users, groups, permissions, sudo            |
| File Types & Metadata     | File types, attributes                      |
| Compression & Archiving   | Tar, gzip, zip utilities                    |
| File Search & Filters     | `grep`, `find`, `locate`, filters           |
| Text Editors              | VIM, nano (add if needed)                   |
| Networking & DNS          | Ping, DNS, IPs, interfaces                  |
| Troubleshooting & Logs    | `journalctl`, logs, services, processes     |
| Scheduling & Automation   | Cron jobs, `at` command                     |
| Disk & Partition Mgmt     | Disk structure, mount, unmount              |
| Firewall & Security Tools | UFW, iptables rules                         |
| Environment Variables     | Export, printenv, sourcing files            |
| Miscellaneous Tools       | Aliases, history, hostname, file transfers  |

--- 

## 🙌 Contributing
Have a command or section you'd like to add? Feel free to open an issue or submit a pull request.

## 📄 License
This project is licensed under the MIT License. You are free to use, modify, and distribute this guide.

## 👤 Author
Maintained by Arya Kashikar.
If you found this helpful, consider ⭐️ starring the repo!


