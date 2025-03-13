# 🔥 Advanced Threat Detection & Performance Testing

## 🚀 Overview
This repository focuses on **functional, performance, and security testing** for web applications. It includes a **detailed analysis** of `http://testphp.vulnweb.com`, covering vulnerabilities, performance bottlenecks, and security risks.

---

## 📂 Project Structure
```
📦 Threat-Detection-Rules/
├── 1. Assignments/
├── 2. Ideation Phase/
├── 3. Requirement Analysis/
│   ├── Customer_Journey_Map.md
│   ├── Data_Flow_Diagram.md
│   ├── Solution_Requirement.md
│   ├── Technology_Stack.md
├── 4. Project Design Phase/
│   ├── Problem_Solution_Fit.md
│   ├── Proposed_Solution.md
│   ├── Solution_Architecture.md
├── 5. Project Planning Phase/
│   ├── Project_Planning_Template.md
├── 6. Project Executable Files/
│   ├── Project_Files/
│   ├── Dataset/
│   ├── Output_Screenshots/
├── 7. Functional and Performance Testing/
│   ├── Performance_Testing.md
│   ├── Performance_Testing_Report.pdf
│   ├── Performance_Testing_Script.js
├── 8. Documentation and Demo/
│   ├── Final_Report.pdf
│   ├── Video_Demo_Link.md
```

---

## 🔎 1. Functional & Security Testing
### 🔹 Tested Pages
1. `/login.php` → User authentication page
2. `/search.php` → Search functionality
3. `/admin.php` → Admin panel access
4. `/cart.php` → Shopping cart manipulation

### ✅ Functional Testing Results
| **Test Case** | **Page** | **Expected Result** | **Actual Result** | **Status** |
|--------------|---------|--------------------|------------------|------------|
| **Valid Login** | `/login.php` | Successful login | ✅ Success | ✅ Pass |
| **Invalid Login** | `/login.php` | Error message displayed | ✅ Error message | ✅ Pass |
| **SQL Injection** | `/login.php` | Should be blocked | ❌ Bypassed login | ❌ Fail |
| **XSS Attack** | `/search.php` | Should prevent script execution | ❌ Alert triggered | ❌ Fail |
| **Admin Access** | `/admin.php` | Should be restricted | ❌ Unauthenticated access | ❌ Fail |

### 🔓 Security Issues Identified
| **Vulnerability** | **Impact** | **Status** |
|------------------|-----------|------------|
| **SQL Injection (SQLi)** | Unauthorized login access | ❌ Vulnerable |
| **Cross-Site Scripting (XSS)** | Executes malicious scripts | ❌ Vulnerable |
| **Admin Panel Access** | No authentication required | ❌ Vulnerable |
| **Weak Session Management** | Open to session hijacking | ❌ Vulnerable |
| **Parameter Tampering** | Modify cart price | ❌ Vulnerable |

📌 **[Full Security Report: `Performance_Testing.md`](./7.%20Functional%20and%20Performance%20Testing/Performance_Testing.md)**  

---

## ⚡ 2. Performance Testing
Performance testing was conducted using **K6 Load Testing Framework**.

### 📌 Load Testing Results (100 Users)
| **Metric** | **Value** | **Status** |
|-----------|----------|------------|
| Avg Response Time | **470ms** | ✅ Pass |
| Peak Response Time | **1100ms** | ❌ Fail |
| Failure Rate | **5.8%** | ❌ Fail |

### 📌 Stress Testing Results
| **Users** | **Avg Response Time** | **Errors (%)** | **Status** |
|-----------|----------------------|---------------|------------|
| 100       | 470ms                | 5.8%          | ✅ Stable  |
| 200       | 780ms                | 12.2%         | ⚠️ Degrading  |
| 300       | 1350ms               | 24.5%         | ❌ Unstable  |
| 400       | 2600ms               | 35%           | ❌ Crashed  |

📌 **[Full Performance Report: `Performance_Testing.md`](./7.%20Functional%20and%20Performance%20Testing/Performance_Testing.md)**  

---

## 🛠 3. Installation & Usage
### 1️⃣ Clone the Repository
```bash
git clone https://github.com/yourusername/Threat-Detection-Rules.git
cd Threat-Detection-Rules
```

### 2️⃣ Run Performance Tests (K6)
Install **K6**:
```bash
npm install -g k6
```
Run the test:
```bash
k6 run 7.Functional\ and\ Performance\ Testing/Performance_Testing_Script.js
```

### 3️⃣ Run Security Tests (SQLi, XSS)
#### SQL Injection Testing (SQLmap)
```bash
sqlmap -u "http://testphp.vulnweb.com/login.php" --dbs
```
#### XSS Testing (Burp Suite)
1. Open **Burp Suite**.
2. Go to **Proxy → Intercept**.
3. Enter payload:  
   ```html
   <script>alert('XSS')</script>
   ```
4. Forward the request and observe execution.

---

## 🔧 4. Security & Performance Fixes (To-Do)
✅ **Security Fixes**
1. **Fix SQL Injection** – Implement parameterized queries and input validation.
2. **Prevent XSS Attacks** – Escape & sanitize user inputs.
3. **Secure Admin Panel** – Implement authentication & access control.
4. **Strengthen Session Management** – Enforce session expiration.

✅ **Performance Fixes**
1. **Optimize Database Queries** – Use indexing and query caching.
2. **Enable Caching & Compression** – Use Gzip & CDN for faster response times.
3. **Optimize Server Load Handling** – Implement load balancing.

📌 **[Security Recommendations](./7.%20Functional%20and%20Performance%20Testing/Performance_Testing.md)**  

---

## 📃 5. License
This project is licensed under the **MIT License**.

---

## 📞 6. Contact
- **GitHub Issues:** [Open an Issue](https://github.com/yourusername/Threat-Detection-Rules/issues)
- **Email:** security@yourdomain.com

---

🚀 **Contribute to Secure Web Applications!** 🔥

