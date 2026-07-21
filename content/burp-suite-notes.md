---
date: 2026-07-20
slug: burp-suite-notes
tags: cybersecurity, burp-suite, web-security, pentesting
title: My Burp Suite Notes for Web Security Testing
---

# My Burp Suite Notes for Web Security Testing
Burp Suite is one of the tools I use while learning and practicing web
application security.
Instead of treating Burp Suite as a collection of buttons, I find it
more useful to understand where each tool fits into the process of
analyzing an HTTP request and testing application behavior.

## Proxy
The Proxy allows HTTP and HTTPS traffic between the browser and web
application to be intercepted.

``` 
Browser
   ↓
Burp Proxy
   ↓
Web Application
```

This allows me to inspect exactly what the browser sends to the server.
Useful things to examine include:
-   HTTP methods
-   URL parameters
-   POST parameters
-   Cookies
-   Authentication tokens
-   HTTP headers
-   API requests
-   JSON data
-   Server responses

## HTTP History
HTTP History records requests passing through Burp.
I usually look for endpoints involving:
-   Login
-   Registration
-   Password reset
-   Account settings
-   File uploads
-   Search functionality
-   Administrative functionality
-   API endpoints
-   User-controlled identifiers

## Repeater
Repeater is one of the most important tools for manual web security
testing.
The workflow is simple:
1.  Find an interesting request.
2.  Send it to Repeater.
3.  Modify one parameter.
4.  Send the request.
5.  Observe the response.
6.  Compare the result.
7.  Repeat.
Changing one thing at a time makes application behavior easier to
understand.

## Intruder
Intruder can automate sending multiple variations of a request.
Potential uses during authorized testing include:
-   Testing multiple parameter values
-   Fuzzing input fields
-   Discovering interesting application behavior
-   Testing predefined payload lists
-   Enumerating predictable values
Automation should not replace understanding the application.

## Decoder
Decoder helps transform encoded data.
Common formats include:
-   URL encoding
-   Base64
-   Hexadecimal
-   HTML encoding
For example:
``` 
YWRtaW4=
```

decodes from Base64 to:
``` 
admin
```
Encoding is not the same thing as encryption.

## Comparer
Comparer helps identify differences between pieces of data.
This can be useful when two HTTP responses appear almost identical but
behave differently.

## Burp Collaborator
Burp Collaborator is useful when testing vulnerabilities that may cause
an application to interact with an external system.
Potential testing scenarios include:
-   Blind command injection
-   Server-side request forgery
-   Certain XML external entity behaviors
-   Out-of-band application interactions

## My Testing Approach
Instead of immediately launching automated scans, I prefer this general
workflow:
1.  Browse the application.
2.  Understand its functionality.
3.  Map important endpoints.
4.  Inspect requests and responses.
5.  Identify user-controlled input.
6.  Send interesting requests to Repeater.
7.  Change one variable at a time.
8.  Observe application behavior.
9.  Form a hypothesis.
10. Test the hypothesis.

## Important Lesson
Burp Suite is powerful, but knowing Burp Suite is not the same thing as
knowing web security.
The deeper skills are understanding:
-   HTTP
-   Authentication
-   Sessions
-   Access control
-   Browser behavior
-   Application logic
-   APIs
-   Encoding
-   Input handling
-   Server-side behavior
Tools change. Fundamentals remain useful.

---

*These notes are intended for learning and authorized security testing.*
