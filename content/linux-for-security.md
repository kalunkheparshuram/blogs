---
date: 2026-07-19
slug: linux-for-security
tags: linux, cybersecurity, fundamentals, networking
title: Linux Fundamentals I Keep Using in Cybersecurity
---

# Linux Fundamentals I Keep Using in Cybersecurity
Linux appears almost everywhere in cybersecurity.
Security distributions such as Kali Linux provide many useful tools, but
knowing how to operate the underlying Linux system is more valuable than
simply knowing the names of those tools.

## Who Am I?
To display the current user:
```
whoami
```
Another useful command is:
```
id
```
The `id` command provides information about the current user's UID, GID,
and group memberships.

## System Information
```
uname -a
```
Operating system information can often be found using:
```
cat /etc/os-release
```

## Current Directory
```
pwd
```
List files:

```
ls
```
Include hidden files and additional information:
```
ls -la
```

## Navigating Directories
```
cd /path/to/directory
cd ..
cd ~
```

## Reading Files
```
cat filename.txt
less filename.txt
head filename.txt
tail filename.txt
```

Follow a changing log file:
```
tail -f logfile.log
```

## Searching Files
Find files by name:
```
find /path -name "filename"
```
Search text inside files:
```
grep "text" filename
```
Recursive search:
```
grep -R "text" /path/
```

## Processes
View running processes:
```
ps aux
```
Another useful tool is:
```
top
```

## Network Interfaces
```
ip addr
```
or:
```
ip a
```

Display routing information:
```
ip route
```

## Listening Ports
```
ss -tulpn
```

Understanding the relationship is important:
```
Process
   ↓
Service
   ↓
Listening Socket
   ↓
Port
   ↓
Network
```

## File Permissions
```
ls -l
```

A result might look like:
```
-rwxr-xr-- 1 user user 1024 file.sh
```

The basic permission types are:
```
r = read
w = write
x = execute
```

Permissions apply to the owner, group, and others.

## Pipes
A pipe sends the output of one command into another:
```
ps aux | grep nginx
```
The mental model is:
```
ps aux
   ↓
output
   ↓
grep nginx
   ↓
filtered output
```

## Redirection
Overwrite a file:
```
echo "hello" > test.txt
```

Append to a file:
```
echo "world" >> test.txt
```

## Why Fundamentals Matter
Installing Kali Linux does not automatically provide Linux knowledge.
Knowing how to use:
-   Files
-   Directories
-   Permissions
-   Users
-   Groups
-   Processes
-   Services
-   Networking
-   Pipes
-   Redirection
-   Shell commands
creates a much stronger foundation for security work.

*Learn what the tool is doing underneath, not only which command to
copy.*

---

*These are personal learning notes that I will continue expanding as I
improve my Linux skills.*
