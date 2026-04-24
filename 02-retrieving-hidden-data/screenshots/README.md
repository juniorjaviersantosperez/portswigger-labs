# SQL Injection - Retrieving Hidden Data

## 📌 Platform
PortSwigger Web Security Academy

## 🎯 Objective
Exploit a SQL injection vulnerability to retrieve hidden products from the database.

## 🧠 Vulnerability
SQL Injection in the WHERE clause of a product filtering query.

## 💥 Payload
' --

## 🛠️ Exploitation Steps
1. Accessed product categories
2. Identified the `category` parameter in the URL
3. Tested with a single quote (') to detect possible SQL injection
4. Injected SQL comment (`--`) to remove part of the query
5. Bypassed the filtering condition and displayed hidden products

## 🧠 Explanation
The SQL comment operator (`--`) was used to remove the filtering condition (`AND released = 1`), allowing hidden products to be displayed.

## 📸 Evidence
See screenshots in the `/screenshots` folder.

## ✅ Result
Successfully retrieved hidden products by manipulating the SQL query.

## 🔐 Mitigation
- Use parameterized queries (prepared statements)
- Validate and sanitize user inputs
- Avoid dynamic SQL queries
