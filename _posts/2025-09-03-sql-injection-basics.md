---
layout: post
title: "Understanding SQL Injection (Beginner Guide)"
date: 2025-09-03
---

What is SQL Injection (SQLI)

SQL Injection is a web security vulnerability that allows an attacker to interfere with the queries an application makes to its database. In other words, it happens when an attacker can insert or “inject” malicious SQL statements into an input field, which are then executed by the backend database. This can lead to unauthorized access, data theft, data manipulation, or even complete control over the database.

How does SQL Injection work?

Web applications often interact with databases using SQL queries, like:
SELECT * FROM users WHERE username = 'input_username' AND password = 'input_password';

If user input is not properly sanitized, an attacker can input SQL code that alters the intended query.

Example:

Input:

Username: ' OR '1'='1
Password: anything

Query becomes:

SELECT * FROM users WHERE username = '' OR '1'='1' AND password = 'anything';

Here '1'='1' is always true, so the attacker can bypass authentication.

Types of SQL Injection
SQL Injection comes in several types:

a) Classic (In-band) SQLi

The attacker uses the same communication channel to inject and retrieve data.

Two subtypes:

Error-based SQLi: Uses database error messages to gain information.

Union-based SQLi: Uses the UNION SQL operator to retrieve data from other tables.

b) Blind SQLi

Occurs when an application does not show errors or return SQL results directly.

The attacker sends payloads and observes behavioral changes (like page content, delays).

Two subtypes:

Boolean-based Blind SQLi: Determines data based on true/false conditions.

Time-based Blind SQLi: Determines data based on response time delays.

c) Out-of-Band SQLi

The attacker triggers SQL commands that make the database send data to another server (rarely used but effective for exfiltration).

Common Targets
- Login forms (username, password)

- Search boxes

- URL parameters (?id=123)

- HTTP headers or cookies

- APIs accepting database queries

  Potential Consequences

  if successful, SQL injection can lead to:

  -Authentication bypass – login without valid credentials.

  -Data leakage – read sensitive information like passwords or credit cards.

  -Data manipulation – modify, delete, or insert records.

  -Privilege escalation – gain administrative access.

  -Denial of Service – crash the database.

  -Remote code execution – in severe cases, take control of the server.

  Prevention Techniques
  - Parameterized Queries / Prepared Statements
Example (Java with JDBC):
String sql = "SELECT * FROM users WHERE username=? AND password=?";
PreparedStatement stmt = connection.prepareStatement(sql);
stmt.setString(1, username);
stmt.setString(2, password);

-Stored Procedures – Only if implemented safely.

-Input Validation / Whitelisting – Restrict input to expected types.

-Escaping User Input – Use built-in database escaping functions.

-Least Privilege Principle – Database accounts should have minimal permissions.

-Web Application Firewalls (WAFs) – Detect and block SQLi attempts.

-Regular Security Testing – Penetration testing and vulnerability scanning.

Real World Examples 
-Sony Pictures (2011) – Attackers used SQLi to steal user data.

-Heartland Payment Systems (2008) – Sensitive credit card data compromised.

-Many e-commerce sites have historically been exploited via login or search fields.

SQL Injection remains one of the top 10 web application security risks according to OWASP, primarily because it's easy to exploit if developers don’t sanitize inputs properly.


  
