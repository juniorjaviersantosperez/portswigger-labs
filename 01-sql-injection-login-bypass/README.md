# SQL Injection - Login Bypass

## 📌 Description
This lab demonstrates a SQL Injection vulnerability in a login form that allows authentication bypass.

## 🎯 Objective
Log in as the administrator user without knowing the password.

## 🧠 Vulnerability
Improper input handling in SQL query (no sanitization).

## 💥 Payload
administrator'--

## 🛠️ Exploitation Steps
1. Identified login form as injection point
2. Injected SQL payload in username field
3. Used SQL comment to bypass password validation

## 📸 Evidence
(Add screenshots here)

## ✅ Result
Successfully authenticated as administrator.

## 🔐 Mitigation
- Use prepared statements
- Validate and sanitize inputs
- Implement secure authentication logic
