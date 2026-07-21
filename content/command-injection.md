---
date: 2026-07-21
slug: command-injection
tags: cybersecurity, web-security, command-injection, pentesting
title: Understanding OS Command Injection
---

# Understanding OS Command Injection
OS Command Injection, sometimes called **Shell Injection**, is a web
security vulnerability that occurs when an application passes unsafe
user-controlled input to an operating system command.
This can become a critical vulnerability because an attacker may be able
to execute operating system commands with the privileges of the
vulnerable application.

## Simple Example
Imagine a web application that allows a user to check whether a host is
reachable.
The backend might execute something similar to:
```
ping -c 4 example.com
```
If the application directly inserts user input into the command without
properly validating it, an attacker may be able to manipulate the
command.
For example:
```
example.com; whoami
```
The resulting shell command could become:
```
ping -c 4 example.com; whoami
```
Instead of executing only `ping`, the operating system may also execute
`whoami`.

## Why Command Injection Is Dangerous
Depending on the application's privileges and environment, successful
command injection could potentially allow an attacker to:
-   Execute operating system commands
-   Read sensitive files
-   Access application configuration
-   Discover environment variables
-   Enumerate the underlying server
-   Interact with internal services
-   Modify files
-   Steal credentials or secrets
-   Potentially gain deeper access to the system
The actual impact depends heavily on the permissions of the vulnerable
application.

## Common Command Separators
On Linux and Unix-like systems, commonly encountered shell operators
include:
```
&&
||
|
;
```
For example:
```
whoami; id
```
or:
```
whoami && id
```
The exact behavior depends on the shell and application context.

## Detecting Command Injection
During an authorized security assessment, simple commands can help
determine whether input is being passed to the operating system.
Common examples include:
```
whoami
id
uname -a
```
The objective during initial testing should be to confirm the
vulnerability with minimal impact.

## Blind Command Injection
Sometimes the application executes the injected command but does not
return its output in the HTTP response.
This is known as **blind OS command injection**.
One technique is introducing a measurable delay:
```
sleep 5
```
If the server response consistently takes approximately five additional
seconds, it may indicate that the command was executed.
Timing differences alone are not always enough to prove a vulnerability
because network latency and application performance can also affect
response times.

## Out-of-Band Detection
Another technique used during authorized testing is *out-of-band
interaction*.
Instead of expecting command output in the HTTP response, the injected
command causes the target system to interact with a server controlled by
the tester.
Tools such as Burp Collaborator can help detect these interactions
during web application security testing.

## Prevention
Applications should avoid constructing operating system commands using
untrusted user input whenever possible.
Safer approaches include:
-   Avoid invoking shell commands unnecessarily
-   Use programming-language APIs instead of shell utilities
-   Use strict allowlists when user input is unavoidable
-   Validate input according to the expected format
-   Avoid concatenating user input into shell commands
-   Run applications using least-privileged accounts
-   Apply defense-in-depth controls
Escaping input alone should not be treated as the primary security
strategy when a safer API can eliminate the need for shell execution
entirely.

## Key Lesson
Command injection is fundamentally a **trust-boundary problem**.
```
Untrusted Input
      ↓
Application
      ↓
Shell Command
      ↓
Operating System
```
Understanding this data flow is more important than memorizing payloads.
---
*For educational purposes and authorized security testing only.*
