# SQL Injection - UNION Attacks

## 📌 Platform
PortSwigger Web Security Academy

## 📚 Labs Completed

### 01 - SQL injection UNION attack, determining the number of columns returned by the query
- Identified the number of columns using UNION SELECT NULL

### 02 - SQL injection UNION attack, finding a column containing text
- Determined which column supports text data

### 03 - SQL injection UNION attack, retrieving data from other tables
- Extracted usernames and passwords from the users table

### 04 - SQL injection UNION attack, retrieving multiple values in a single column
- Used CONCAT to combine username and password into a single column

---

## 🧠 Skills Demonstrated
- SQL Injection (UNION-based)
- Column enumeration
- Data extraction
- Data concatenation
- Understanding database responses

---

## 📸 Evidence

### Lab 01
- 01-column-count.png
- 02-column-count.png

### Lab 02
- 03-valid-text-column.png

### Lab 03
- 04-1-union-payload.png
- 04-2-union-data.png
- 04-3-union-users-table.png
- 04-4-union-passwords.png
- 04-5-admin-login.png

### Lab 04
- 05-1-union-payload.png
- 05-2-union-data-extracted.png
- 05-3-union-admin-login.png
