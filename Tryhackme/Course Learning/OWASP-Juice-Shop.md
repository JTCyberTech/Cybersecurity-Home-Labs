# Open for business!

Introduction:

- Focus on OWASP's Top 10 vulnerabilities in web applications within the context of Juice Shop.
- Emphasize that Juice Shop, an OWASP creation, will be used for exploration.

Temporary IP Address: [10.10.236.183]

Scope:

- Due to Juice Shop's size, not all Top 10 vulnerabilities will be covered.
- Specify the vulnerabilities to be covered: Injection, Broken Authentication, Sensitive Data Exposure, Broken Access Control, Cross-Site Scripting (XSS).

<h2></h2>

# Let's go on an adventure!

Question #1: What's the Administrator's email address?

`admin@juice-sh.op`

<p align="center"> <img src="https://i.imgur.com/PZrOfpY.png" height="90%" width="90%" alt=""/>

Question #2: What parameter is used for searching? 

`q`

- Find the magnifying glass icon at the top right of the application.
- Click on it to open a search bar.
- Type in `a` into the search bar.
- Press Enter to search for the text.
- Look at the URL, and you'll see the text you entered after /#/search? following the letter "q".

<p align="center"> <img src="https://i.imgur.com/zg2rkfJ.png" height="90%" width="90%" alt=""/>

Question #3: What show does Jim reference in his review? 

`Star Trek`

<h2></h2>

# Inject the juice

Focus on Injection Vulnerabilities: The task centers around injection vulnerabilities, which pose a significant threat to companies, potentially leading to downtime and data loss.

Danger of Injection Vulnerabilities: Injection vulnerabilities can have severe consequences, including the potential for unauthorized access, data manipulation, and account compromise.

Identification of Injection Points: It's often straightforward to identify injection points within a web application as they typically result in error messages. This can serve as an early warning sign for potential vulnerabilities.

Types of Injection Attacks:

- SQL Injection:
  - Attacker enters a malicious query to retrieve or tamper with database data.
  - May also be used to log into accounts.

- Command Injection:
  - Web applications execute user-controlled data as system commands.
  - Attackers can manipulate this data to execute unauthorized system commands, particularly in misconfigured scenarios like ping tests.

- Email Injection:
  - Security vulnerability allowing unauthorized sending of email messages.
  - Occurs when attackers add extra data to fields not correctly interpreted by the email server.
Chosen Focus: SQL Injection: The specific injection method to be explored in this task is SQL Injection, where attackers exploit vulnerabilities to interact with and manipulate a database, potentially leading to unauthorized access or data tampering.

<h2></h2>

Question #1: Log into the administrator account!

`32a5e0f21372bcc1000a6088b93b458e41f0e02a`

Open up Burp Suite > Go to "Proxy" > Click on "Open browser" > Navigate to the Juice Shop Webpage by putting in the IP Address.

<p align="center"> <img src="https://i.imgur.com/dFiOpZD.png" height="90%" width="90%" alt=""/>

Click on the 3 lines on the upper right hand corner of the webpage > Click on "Login".

<p align="center"> <img src="https://i.imgur.com/j8kXcgY.png" height="90%" width="90%" alt=""/>

Type in `a` for Email. And, type in `a` for Password.

<p align="center"> <img src="https://i.imgur.com/R9byBoJ.png" height="90%" width="90%" alt=""/>

Click "Intercept is off" to turn on intercept on Burp Suite > Click "Log in" on the webpage.

<p align="center"> <img src="https://i.imgur.com/Pc793z6.png" height="90%" width="90%" alt=""/>

This will appear on Burp Suite:

<p align="center"> <img src="https://i.imgur.com/P7k9un3.png" height="90%" width="90%" alt=""/>

Change: "email": "a" to `"email":"' or 1=1--"` > Click on the "Forward" button on the top.

<p align="center"> <img src="https://i.imgur.com/Ok5Jt2T.png" height="90%" width="90%" alt=""/>

Turn off the intercept then refresh the webpage.

<p align="center"> <img src="https://i.imgur.com/4XvcIrz.png" height="90%" width="90%" alt=""/>

Why does this work?

- When we use the character ' in an SQL query, it signals the end of a section in the query.
- In a SQL statement, 'OR' means that if either side of it is true, the whole statement is true. So, when we use 'OR 1=1', which is always true, the entire statement becomes true. This tricks the server into thinking the email is valid, and we get logged into user id 0, which is typically the administrator account.
- The -- character in SQL is like putting a comment in code. It's used to comment out data, making any restrictions on login ineffective because they are interpreted as comments. This is similar to using # in Python or // in JavaScript to add comments.

<h2></h2>

Question #2: Log into the Bender account!

`fb364762a3c102b2db932069c0e6b78e738d4066`

Similar to Question 1, just change:

- "email":"' or 1=1--" into `"email":"bender@juice-sh.op'--"`

<p align="center"> <img src="https://i.imgur.com/JUxFKg1.png" height="90%" width="90%" alt=""/>

Refresh the webpage

<p align="center"> <img src="https://i.imgur.com/vGP4bTI.png" height="90%" width="90%" alt=""/>

<h2></h2>

# Who broke my lock?!

Task Objective: Exploiting authentication vulnerabilities through various flaws.

Focus Area: Flaws within authentication mechanisms that are susceptible to manipulation.

Target Mechanisms:

- Weak Passwords: Specifically, targeting high privileged accounts.

Authentication Flaws for Exploitation:

- Weak Passwords in High-Privileged Accounts: Identifying and exploiting vulnerabilities arising from inadequate password strength in accounts with elevated privileges.

Scope:
- Investigating and manipulating mechanisms listed below for exploitation.

<h2></h2>

Question #1: Bruteforce the Administrator account's password!

`c2110d06dc6f81c67cd8099ff0ba601241f1ac0e`

Log out of any user > Navigate to the login page > Type in: `admin@juice-sh.op` for Email > Type in: `a` for Password > Turn Interceptor on Proxy > Click on "Login in"

<p align="center"> <img src="https://i.imgur.com/5g5pDFV.png" height="90%" width="90%" alt=""/>

Click on "Action" on Burp Suite > Select "Send to Intruder".

<p align="center"> <img src="https://i.imgur.com/1wGLhKI.png" height="90%" width="90%" alt=""/>

Navigate to "Intruder" > Change Password from "a" to `§§` by deleting `a` and click on "Add §".

<p align="center"> <img src="https://i.imgur.com/UjW3mfC.png" height="90%" width="90%" alt=""/>

Click on "Payloads" > Click on "Load" > Find "best1050.txt from Seclists" (install via: apt-get install seclists).

<p align="center"> <img src="https://i.imgur.com/EYR8FJW.png" height="90%" width="90%" alt=""/>

Click on "Start attack".

<p align="center"> <img src="https://i.imgur.com/cp92u7c.png" height="90%" width="90%" alt=""/>

Found the password to be: `admin123`.

<p align="center"> <img src="https://i.imgur.com/bre1Rec.png" height="90%" width="90%" alt=""/>

Turn off Interception > Login with the password.

<p align="center"> <img src="https://i.imgur.com/XNRtUO0.png" height="90%" width="90%" alt=""/>

Successfully capture the flag.

<p align="center"> <img src="https://i.imgur.com/hlQgccJ.png" height="90%" width="90%" alt=""/>

<h2></h2>

Question #2: Reset Jim's password!

``

- Surprising Fact: Even the password reset process can be vulnerable!
- Example Scenario: Jim's security question is "Your eldest sibling's middle name?" on the Forgot Password page.
- Previous Discovery (Task 2): Suggests a connection between Jim and Star Trek.
- Current Investigation: Searching "Jim Star Trek" on Google leads to a wiki page about James T. Kirk from Star Trek.

Log out the Admin account > Navigate to the login page > Click on "Forgot your password?`

<p align="center"> <img src="https://i.imgur.com/hlQgccJ.png" height="90%" width="90%" alt=""/>
