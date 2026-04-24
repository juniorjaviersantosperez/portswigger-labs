# SQL Injection - Login Bypass

## 📌 Platform
PortSwigger Web Security Academy

## 🎯 Objective
Exploit a SQL injection vulnerability to bypass authentication and log in as the administrator user.

## 🧠 Vulnerability
The login form is vulnerable to SQL injection due to improper input sanitization.

## 💥 Payload
administrator'--

## 🛠️ Exploitation Steps
1. Accessed the login page
2. Identified username input as injection point
3. Injected SQL payload: `administrator'--`
4. Bypassed password validation

## 📸 Evidence
See screenshots in the `/screenshots` folder.

## ✅ Result
Successfully logged in as the administrator user without knowing the password.

## 🔐 Mitigation
- Use parameterized queries (prepared statements)
- Validate and sanitize all user inputs
- Implement secure authentication mechanisms
