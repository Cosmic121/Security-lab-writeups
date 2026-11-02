
# Lab: File path traversal, simple case

**Platform:** PortSwigger Web Security Academy
**Difficulty:** Apprentice
**Category:** Path Traversal

## Objective

Retrieve the contents of /etc/passwd file stored inside the server's filesystem.

## Vulnerability

The application contains a path traversal vulnerability.

## Exploitation

### Steps

1. While inspecting the requests made by the client, I noticed the browser requesting for the image for the webpage from the server.
The request was 'GET /image?filename=37.jpg HTTP/2'.
2. Since the application is known to be vulnerable to path traversal, I tried modifying the filename parameter.
3. I used the payload '../../../etc/passwd', exchanging it with 37.jpg. The new crafted request being 
GET /image?filename=../../../etc/passwd HTTP/2
4. After sending the request, I could access the /etc/passwd file.

### Payload

```text
../../../etc/passwd
```

## Root Cause

The root cause for the vulnerability being, the server accepts user modified requests to build the path and doesn't restricts file traversal outside the intended directory.

## Remediation

The server shouldn't trust user crafted parameters inside the directory's path.

## Key Takeaway

I learned how path traversal is performed and what measures one should opt to make their system secure.
