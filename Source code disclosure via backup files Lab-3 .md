# ✅ Lab 3: Source Code Disclosure via Backup Files

## 🎯 Objective

The objective of this lab is to discover a **hard-coded database password** that has been inadvertently leaked through a **backup file** located in a hidden directory.

> **Goal:** Find and submit the database password from the exposed backup file to complete the lab.

---

## 🧭 Step-by-Step Solution

### 1. 🌐 Launch the Lab

- Click the **"Access the Lab"** button on the Web Security Academy.
- The target web application will open in a new browser tab.


---

### 2. 🔍 Discover Hidden or Backup Directories

Explore the web application manually or use tools like **Burp Suite**, **ffuf**, or **dirb** to identify hidden directories or files.

#### 🎯 Common Paths to Check:

- `/robots.txt`
- `/backup/`
- `/static/`
- `/.git/`

#### ✅ Example:

Visit:


If the output shows:


➡️ This reveals a sensitive directory `/backup/` that should be investigated.

---

### 3. 📂 Access the Backup Directory

Navigate to the `/backup/` directory:

You may find files like:

---

### 4. 📝 Retrieve and Analyze the Backup File

Open or download the backup file:

Carefully inspect the source code for hardcoded secrets.

#### 🔍 Look for keywords:
- `dbPassword`
- `secret`
- `credentials`

---

### 📌 Example Code Snippet:
```java
String dbPassword = "s3cr3tP@ssw0rd123";
