# SQL Injection

# What is SQL Injection?

SQL Injection (SQLi) is a web security vulnerability that allows an attacker to interfere with the queries that an application sends to its database. This can allow an attacker to gain access to data that they normally cannot access. This can be data belonging to other users, or any other data that the application has access to.

![PortSwigger](../Drawing/Drawing_2.png)
![PortSwigger](../Drawing/Drawing_1.png)

Before studying practical attacks, it is important to understand the fundamental principles of SQL injection: how SQL queries are formed, where vulnerabilities occur, and how incorrect processing of user input leads to data compromise.

## Detecting SQL Injection Vulnerabilities

SQL Injection vulnerabilities can be detected by testing different application inputs and analyzing how the system responds to specially crafted SQL expressions.

Main detection methods:

- **Single quote (`'`)** — helps identify SQL errors or unexpected behavior.
- **Boolean tests (`OR 1=1`, `OR 1=2`)** — determine whether user input affects SQL queries.
- **Response comparison** — different SQL conditions may cause changes in application behavior.
- **Time-based checks** — delays in query execution can reveal blind SQL Injection.
- **OAST (Out-of-Band)** — external interactions such as DNS/HTTP requests can confirm vulnerabilities without visible output.

Burp Suite Scanner can also be used to automatically detect common SQL Injection vulnerabilities.
