
# 🧪 Lab: Authentication Bypass via Information Disclosure

## 🎯 Objective

The goal of this lab is to exploit an authentication bypass vulnerability that relies on a custom HTTP header. By discovering and forging this header, we can gain unauthorized access to the admin panel and delete the user `carlos`.

---

## 🧠 Vulnerability Overview

The web application uses a custom HTTP header to determine whether a request originates from a trusted internal source (e.g., `127.0.0.1`). This header is unintentionally exposed through insecure HTTP methods such as `TRACE`, allowing attackers to spoof trusted requests.

---

## 🛠️ Exploitation Steps

### 1. Access the Lab and Log In

- Open the lab website.
- Log in with the provided credentials:

```text

## Lab: Authentication Bypass via Information Disclosure

### 2. Locate the Admin Interface

Attempt to access the admin panel directly by navigating to:


This will return a **403 Forbidden** error, indicating that access is restricted.

---

### 3. Intercept the Request with Burp Suite

- Capture the `/admin` request using Burp Suite.
- Send the captured request to the **Repeater** tab for further analysis.

---

### 4. Enumerate HTTP Methods

- In the Repeater tab, change the HTTP method to `TRACE` or `OPTIONS`:


- Check the response headers for something like:


This indicates that the application trusts requests containing this header.

---

### 5. Bypass Authentication

- Return to the original `/admin` GET request in Repeater.
- Add the following header:


- Send the modified request.
- If successful, the response will be **200 OK**, granting access to the admin interface.

---

### 6. Delete the User *carlos*

- Navigate to the user management section within the admin panel.
- Locate the user named `carlos`.
- Delete the user and confirm the action.
- This completes the lab.

✅ The lab is now solved.

---

### 🔐 Mitigation & Best Practices

- Do **not** rely on client-supplied headers (such as `X-Forwarded-For`) for authentication or authorization decisions.
- Disable insecure HTTP methods like `TRACE`, `TRACK`, and `OPTIONS` on production servers.
- Enforce strict server-side access controls for sensitive endpoints like `/admin`.

---


