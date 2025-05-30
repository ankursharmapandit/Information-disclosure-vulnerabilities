# 🔍 Lab 1: Information Disclosure in Error Messages

## ✅ What is Information Disclosure?
Information disclosure (also known as *information leakage*) occurs when a web application unintentionally reveals sensitive information to users or potential attackers. This can include:

- 🧑‍💼 Personal data (usernames, emails, financial details)
- 🏢 Business-sensitive logic or metadata
- 🧱 Technical information (server paths, version numbers, source code)

---

## 🧪 Common Examples of Information Disclosure

1. **Directory Listings**  
   Accessible `/robots.txt` or unprotected directories may expose internal structures.

2. **Backup or Source Files**  
   Files like `.bak`, `.zip`, `.git`, or temporary uploads often contain source code or credentials.

---

## ⚠️ Impact of Information Disclosure Vulnerabilities

Such vulnerabilities can result in:

- 📂 Unauthorized access to internal data or services  
- 🛠️ Exploitation of known framework vulnerabilities  
- 💸 Reputational and financial damage due to data leaks  

---

## 🧪 Lab Objective

**Lab Title:** Information Disclosure in Error Messages  
**Goal:** Identify and submit the version number of a vulnerable third-party framework leaked in an error message.

---

## 🛠️ Step-by-Step Solution

### 1. 🌐 Launch the Lab
Open the lab from the PortSwigger Web Security Academy platform.

### 2. 🧰 Configure Burp Suite
Ensure your browser is set up to proxy traffic through **Burp Suite**.

### 3. 🛒 Navigate to a Product Page
Browse any product listing on the lab site to generate a dynamic request.

### 4. 🎯 Intercept the Request
Using Burp Suite's **Proxy > Intercept** tab, capture the product request.

### 5. ✏️ Modify the Product ID
Edit the request to use an invalid or malformed `productId`, such as:


### 6. 📤 Forward the Request
Forward the modified request and observe the response from the server.

### 7. 👀 Analyze the Error Message
Check for a verbose error message. Look for:
- Stack traces
- Java class references
- Framework or library names and **version numbers**  
  Example:

### 8. 📝 Submit the Version Number
Copy the version number and submit it in the solution box provided in the lab interface.

---

## ✅ Final Notes

Verbose error messages provide valuable reconnaissance data to attackers. Always configure error handling mechanisms to:
- Display generic error messages to users
- Log detailed errors server-side only

---

## 📁 Example Output for Submission

If the error reveals:
```java
org.apache.struts2.StrutsException: Something went wrong
Struts version: 2.3.15
