Lab 04: Blind SQL Injection with Conditional Responses
📌 Description

This lab contains a blind SQL injection vulnerability, where the application does not return database results or display errors.

However, the application response changes depending on whether the query returns results, showing a "Welcome back" message when the condition is true.

The goal is to exploit this vulnerability to retrieve the password of the administrator user and log in.

🎯 Objective
Identify the blind SQL injection vulnerability
Determine the password length
Extract the password character by character
Log in as administrator
⚙️ Methodology
Validate the injection using boolean conditions (TRUE / FALSE)
Confirm the existence of the users table
Verify the administrator user
Enumerate the password length
Extract the password using SUBSTRING()
Automate the process with Burp Suite Intruder
Log in using the obtained credentials
🛠️ Tools Used
Burp Suite (Proxy, Repeater, Intruder)
📂 Evidence

The results and screenshots for this lab are located in the following folder:

/screenshots
🚀 Status

✅ Completed
