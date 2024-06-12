# SQL-Injection-Attack-on-Application
One kind of security flaw called SQL injection lets an attacker tamper with the queries a program sends to its database. This may lead to data being accessed without authorization, data being able to be changed or removed, and in certain situations, even performing administrative actions on the database.

1. Frequently, an application uses user input to populate SQL queries. For instance, a login form may utilize a query to verify the accuracy of the credentials by using the username and password.
   SELECT * FROM Users WHERE username = '' AND password = '';

2. By manipulating user input, an attacker can insert SQL commands. For instance, the query becomes: if the attacker inputs 'OR '1'='1 as the username and omits the password.
   SELECT * FROM Users WHERE username = '' OR '1'='1' AND password = '';
   Since 1=1 is always accurate, this query always returns true, enabling the attacker to get around authentication.

3. The database executes the injected SQL, which may result in data corruption, data leaks, or other malicious activities.

Solution:
-Use Prepared Statements (Parameterized Queries): Make sure that SQL queries do not contain direct user input. Use placeholders and bind parameters instead.
-Validate and sanitize inputs by making sure they fit expected patterns and excluding potentially harmful characters.
