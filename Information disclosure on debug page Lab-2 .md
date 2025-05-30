# 🧪 Lab 2: Information Disclosure on Debug Page

## 🎯 Objective

This lab demonstrates how an exposed **debug page** can leak sensitive application information.

**Goal:** Find and submit the value of the `SECRET_KEY` environment variable.

---

## 🧠 What’s the Vulnerability?

Debug pages are intended for developers to troubleshoot issues during development. When accidentally left accessible in a production environment, they can reveal critical internal details, including:

- 🔐 Environment variables  
- 🗂️ File paths and system configuration  
- ⚙️ Server-side code and framework versions  

### 📌 In this lab:
A debug page is leaking the `SECRET_KEY` variable, which can lead to:

- Forging session tokens
- Unauthorized access
- Exploitation of app logic

---

## 🛠️ Step-by-Step Solution

### 1. 🌐 Open the Lab Website
Launch the lab from [PortSwigger Web Security Academy](https://portswigger.net/web-security). It will open the target website in your browser.

---

### 2. 🧰 Launch Burp Suite
Ensure your browser is correctly configured to route traffic through **Burp Suite**.

---

### 3. 🎯 Capture a Request
- Visit any page on the website (e.g., homepage or product page).
- Capture the request using **Burp Proxy > Intercept**.

---

### 4. 📍 Explore the Site Map
- Go to **Target → Site Map** in Burp Suite.
- Expand the domain to explore endpoints.

---

### 5. 🔎 Use Engagement Tools
- Right-click the domain in the Target tab.
- Select:


---

### 6. 📁 Look for Sensitive Debug Files
Check for commonly exposed debug-related files or directories, such as:


---

### 7. 🚀 Send Suspicious Files to Repeater
- Right-click on a file like `phpinfo.php`.
- Click **Send to Repeater**.

---

### 8. 🔍 Analyze the Response
- In the **Repeater** tab, send the request.
- Carefully scroll through the HTML response to find the environment variable.

#### 🔐 Example:
```bash
SECRET_KEY=flasklab-8392748289-secret
