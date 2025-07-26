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


* `echo $SHELL` – Displays the current shell.
* `chsh -s /bin/bash` – Changes the login shell to Bash.
* `cat /etc/shells` – Lists available shells.

## 3. Bash Shell Functions

* `function greet() { echo "Hello $1"; }` – Defines a Bash function.
* `greet Arya` – Calls the `greet` function with argument.
* `declare -f` – Lists all defined functions.

## 4. Getting Help in Shell

* `man ls` – Opens manual page for `ls` command.
* `ls --help` – Displays help for `ls` command.
* `whatis ls` – Gives a one-line description.
* `apropos list` – Searches man pages for related commands.

## 5. File and Directory Management

* `touch file.txt` – Creates an empty file.
* `mkdir folder` – Creates a directory.
* `rm file.txt` – Deletes a file.
* `rm -r folder` – Deletes a directory recursively.
* `cp file1.txt file2.txt` – Copies a file.
* `mv file1.txt file2.txt` – Renames or moves a file.
* `cat > file.txt` – Writes input to file (overwrite).
* `echo "Text" >> file.txt` – Appends text to file.

## 6. Core Linux System

* `uname -a` – Displays system information.
* `top` – Displays active processes.
* `df -h` – Shows disk usage.
* `free -m` – Displays memory usage.

## 7. Linux Kernel

* `uname -r` – Displays the kernel version.
* `cat /proc/version` – Shows detailed kernel version info.

## 8. User and Permissions Management

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

* `sudo command` – Runs command with superuser privileges.
* `sudo su` – Switches to root user.

## 10. Run Levels / Systemd Targets

* `runlevel` – Shows the current run level.
* `systemctl get-default` – Shows default systemd target.
* `systemctl set-default multi-user.target` – Sets CLI runlevel.
* `systemctl isolate graphical.target` – Switches to GUI mode.

## 11. File Types and Metadata

* `ls -l` – Lists file details including type.
* `file filename` – Displays file type.

## 12. Package Management

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

* `for i in {1..5}; do echo $i; done` – Loop in shell.
* `if [ -f file.txt ]; then echo "Exists"; fi` – Conditional in shell.
* `while true; do echo hello; sleep 1; done` – Infinite loop example.

## 14. Compression and Archiving

* `tar -cvf archive.tar file1 file2` – Creates a tar archive.
* `tar -xvf archive.tar` – Extracts a tar archive.
* `gzip file.txt` – Compresses a file.
* `gunzip file.txt.gz` – Decompresses a gzip file.
* `zip file.zip file1 file2` – Creates a zip archive.
* `unzip file.zip` – Extracts a zip archive.

## 15. File Searching and Filtering

* `grep "text" file.txt` – Searches for text in file.
* `find . -name file.txt` – Finds file by name.
* `locate filename` – Quickly finds files by name (uses DB).

## 16. Text Editors – VIM

* `vim file.txt` – Opens file in VIM.
* `i` – Insert mode.
* `Esc + :w` – Save file.
* `Esc + :q` – Quit.
* `Esc + :wq` – Save and quit.

## 17. Networking and DNS

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

* `crontab -e` – Edits scheduled jobs.
* `at now + 5 minutes` – Schedules a one-time task.

## 20. Disk and Partition Management

* `lsblk` – Lists block devices.
* `fdisk -l` – Displays disk partition table.
* `mount /dev/sda1 /mnt` – Mounts partition.
* `umount /mnt` – Unmounts partition.

## 21. Firewall and Security Tools

* `ufw enable` – Enables uncomplicated firewall.
* `ufw allow 22` – Allows SSH traffic.
* `ufw status` – Displays firewall status.
* `iptables -L` – Lists current iptables rules.

## 22. Environment Variables

* `export VAR=value` – Sets a variable for session.
* `echo $VAR` – Displays value of a variable.
* `printenv` – Prints environment variables.
* `source ~/.bashrc` – Reloads bash config.

## 23. Additional Useful Commands

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



