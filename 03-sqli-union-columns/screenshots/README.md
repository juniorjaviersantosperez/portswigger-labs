# SQL Injection - Determining Number of Columns

📌 Platform
PortSwigger Web Security Academy

🎯 Objective
Determine the number of columns returned by the original SQL query using a UNION-based SQL injection.

🧠 Vulnerability
SQL Injection in the URL parameter (category), allowing manipulation of the SQL query.

💥 Payload
' UNION SELECT NULL,NULL,NULL--

🛠️ Exploitation Steps
Accessed a product category
Identified the category parameter in the URL
Tested SQL injection using a single quote (')
Injected UNION SELECT with increasing NULL values
Observed application responses to detect errors
Identified the correct number of columns when the page loaded successfully

🧠 Explanation
The UNION SELECT statement requires the same number of columns as the original query.
By incrementing the number of NULL values, it was possible to determine the correct column count when the query executed without errors.

📸 Evidence
See screenshots in the /screenshots folder.

✅ Result
Successfully determined that the original query contains **3 columns**.

🔐 Mitigation
Use parameterized queries (prepared statements)
Validate and sanitize user inputs
Avoid exposing database errors
