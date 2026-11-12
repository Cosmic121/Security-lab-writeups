
# Lab Name: User role controlled by request parameter

**Platform:** PortSwigger Web Security Academy
**Difficulty:** Apprentice
**Category:** Access Control

## Objective

Accessing the admin panel of an application and deleting a user.

## Vulnerability

The application identifies administration through forgeable cookies.

## Exploitation

### Steps

1. I tried accessing the admin panel by logging in with the credentials provided, since the user doesn't have administration privilege I was unable to access the webpage.
2. I modified the value of admin cookie of the current user from False to True.
3. After changing the value and refreshing the page, I could access the admin panel.
4. I deleted user carlos through admin functionality, clearing the lab. 

### Payload

```text
Admin=True
```

## Root Cause

The application trusting client-side authorization instead of server-side authorization

## Remediation

Never trust client side authorization such as forgeable cookies and it's values. Instead make the application trust server-side authorization.

## Key Takeaway

I learned how forging cookies can grant access to important functionalities if the application trusts client side authorization.
