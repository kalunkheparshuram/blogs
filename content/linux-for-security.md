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

``` bash
whoami
```

Another useful command is:

``` bash
id
```

The `id` command provides information about the current user's UID, GID,
and group memberships.

## System Information

``` bash
uname -a
```

Operating system information can often be found using:

``` bash
cat /etc/os-release
```

## Current Directory

``` bash
pwd
```

List files:

``` bash
ls
```

Include hidden files and additional information:

``` bash
ls -la
```

## Navigating Directories

``` bash
cd /path/to/directory
cd ..
cd ~
```

## Reading Files

``` bash
cat filename.txt
less filename.txt
head filename.txt
tail filename.txt
```

Follow a changing log file:

``` bash
tail -f logfile.log
```

## Searching Files

Find files by name:

``` bash
find /path -name "filename"
```

Search text inside files:

``` bash
grep "text" filename
```

Recursive search:

``` bash
grep -R "text" /path/
```

## Processes

View running processes:

``` bash
ps aux
```

Another useful tool is:

``` bash
top
```

## Network Interfaces

``` bash
ip addr
```

or:

``` bash
ip a
```

Display routing information:

``` bash
ip route
```

## Listening Ports

``` bash
ss -tulpn
```

Understanding the relationship is important:

``` text
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

``` bash
ls -l
```

A result might look like:

``` text
-rwxr-xr-- 1 user user 1024 file.sh
```

The basic permission types are:

``` text
r = read
w = write
x = execute
```

Permissions apply to the owner, group, and others.

## Pipes

A pipe sends the output of one command into another:

``` bash
ps aux | grep nginx
```

The mental model is:

``` text
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

``` bash
echo "hello" > test.txt
```

Append to a file:

``` bash
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

**Learn what the tool is doing underneath, not only which command to
copy.**

------------------------------------------------------------------------

*These are personal learning notes that I will continue expanding as I
improve my Linux skills.*
