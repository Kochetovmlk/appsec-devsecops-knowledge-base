# SQL Injection

# What is SQL Injection?

SQL Injection (SQLi) is a web security vulnerability that allows an attacker to interfere with the queries that an application sends to its database. This can allow an attacker to gain access to data that they normally cannot access. This can be data belonging to other users, or any other data that the application has access to.

![PortSwigger](../Drawing/Drawing_2.png)
![PortSwigger](../Drawing/Drawing_1.png)

Before studying practical attacks, it is important to understand the fundamental principles of SQL injection: how SQL queries are formed, where vulnerabilities occur, and how incorrect processing of user input leads to data compromise.

# Threat Map: Types of SQL Injection

Before diving deeper into exploit development, let's first understand the "map of the territory". SQL Injection is not a single vulnerability — it can be divided into different types depending on how an attacker receives information from the server.

The diagram below serves as our guide. It clearly separates SQL Injection attacks into three main categories:

**In-Band SQL Injection** — the "fast and loud" approach: errors or extracted data are returned directly in the application's response.

**Blind (Inferential) SQL Injection** — the "quiet and slow" approach: no data is directly visible, but the attacker can infer information by analyzing application behavior (true/false conditions or response delays).

**Out-of-Band SQL Injection** — used when standard communication channels are unavailable. Data is extracted through alternative channels, such as DNS or HTTP interactions.

This classification is essential because it defines not only the complexity of the attack but also the appropriate defense strategy.

![PortSwigger](../Drawing/Drawing_3.png)

## Detecting SQL Injection Vulnerabilities

SQL Injection vulnerabilities can be detected by testing different application inputs and analyzing how the system responds to specially crafted SQL expressions.

Main detection methods:

- **Single quote (`'`)** — helps identify SQL errors or unexpected behavior.
- **Boolean tests (`OR 1=1`, `OR 1=2`)** — determine whether user input affects SQL queries.
- **Response comparison** — different SQL conditions may cause changes in application behavior.
- **Time-based checks** — delays in query execution can reveal blind SQL Injection.
- **OAST (Out-of-Band)** — external interactions such as DNS/HTTP requests can confirm vulnerabilities without visible output.

Burp Suite Scanner can also be used to automatically detect common SQL Injection vulnerabilities.
