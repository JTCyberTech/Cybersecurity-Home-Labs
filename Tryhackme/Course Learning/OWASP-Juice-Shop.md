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

<h3>Injection </h3>

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

<h3>Broken Autherntication</h3>

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

`094fbc9b48e525150ba97d05b942bbf114987257`

- Surprising Fact: Even the password reset process can be vulnerable!
- Example Scenario: Jim's security question is "Your eldest sibling's middle name?" on the Forgot Password page.
- Previous Discovery (Task 2): Suggests a connection between Jim and Star Trek.
- Current Investigation: Searching "Jim Star Trek" on Google leads to a wiki page about James T. Kirk from Star Trek.

Log out the Admin account > Navigate to the login page > Click on "Forgot your password?`

<p align="center"> <img src="https://i.imgur.com/Vs4LtIL.png" height="90%" width="90%" alt=""/>

Put in Jim's Email: `jim@juice-sh.op` > Security question asked "Your eldest silbings middle name?" > Go on wiki search "jim star trek" > Found `Samuel` to be the answer > Create New Password > Change.

<p align="center"> <img src="https://i.imgur.com/MRChoYc.png" height="90%" width="90%" alt=""/>

Successfully capture the flag.

<p align="center"> <img src="https://i.imgur.com/3FJJW49.png" height="90%" width="90%" alt=""/>

<h2></h2>

# AH! Don't look!

<h3>Sensitive Data Exposure</h3>

A good web application needs to keep sensitive information safe. Unfortunately, sometimes developers don't do this properly, and it leaves the data open to potential risks.

Often, the protection of data is not the same throughout the whole web application, which means some pages might be accessible to anyone. Additionally, there are cases where information is accidentally shared with the public without the developer knowing, making the web application more prone to attacks.

<h2></h2>

Question #1: Access the Confidential Document!

`edf9281222395a1c5fee9b89e32175f1ccf50c5b`

Click on the three lines on the upper left corner of the webpage > Click on "About Us".

<p align="center"> <img src="https://i.imgur.com/lDhQnEs.png" height="90%" width="90%" alt=""/>

Click on the green text.

<p align="center"> <img src="https://i.imgur.com/qv2yRFC.png" height="90%" width="90%" alt=""/>

Edit the URL: `http://10.10.236.183/ftp`

<p align="center"> <img src="https://i.imgur.com/ntmRl1E.png" height="90%" width="90%" alt=""/>

Download "acquisitions.md" and save it > Navigate to the home page.

<p align="center"> <img src="https://i.imgur.com/868ALTn.png" height="90%" width="90%" alt=""/>

Successfully capture the flag.

<p align="center"> <img src="https://i.imgur.com/Lz7pHEf.png" height="90%" width="90%" alt=""/>

<h2></h2>

Question #2: Log into MC SafeSearch's account!

`66bdcffad9e698fd534003fbb3cc7e2b7b55d7f0`

https://youtu.be/v59CX2DiX0Y?si=Yq9tXpMyxcSXzkvm&t=38

He notes that his password is "Mr. Noodles" but he has replaced some "vowels into zeros", meaning that he just replaced the o's into 0's.

We now know the password to the mc.safesearch@juice-sh.op account is "Mr. N00dles"

Login with the Email and Password.

<p align="center"> <img src="https://i.imgur.com/TnZlBDg.png" height="90%" width="90%" alt=""/>

Successfully captured the flag.

<p align="center"> <img src="https://i.imgur.com/xBhdqlo.png" height="90%" width="90%" alt=""/>

<h2></h2>

Question #3: Download the Backup file!

``

We will now go back to the  http://10.10.236.183/ftp/ folder and try to download package.json.bak. But it seems we are met with a 403 which says that only .md and .pdf files can be downloaded. 

<p align="center"> <img src="https://i.imgur.com/KcL6BPE.png" height="90%" width="90%" alt=""/>

To get around this, we will use a character bypass called "Poison Null Byte". A Poison Null Byte looks like this: %00. 

Note: as we can download it using the url, we will need to encode this into a url encoded format.

The Poison Null Byte will now look like this: %2500. Adding this and then a .md to the end will bypass the 403 error!

<p align="center"> <img src="https://i.imgur.com/8IFUOcP.png" height="90%" width="90%" alt=""/>

Navigate back to the home page > Successfully captured the flag.

<p align="center"> <img src="https://i.imgur.com/bJMC421.png" height="90%" width="90%" alt=""/>

<h2></h2>

# Who's flying this thing?

<h3>Broken Access Control</h3>

In modern systems, several users can access various pages. Typically, administrators use a special page to change, add, or delete elements on a website. This is common when using website-building tools like Weebly or Wix.

If there are issues or bugs related to Broken Access Control, they fall into two categories:

Horizontal Privilege Escalation:
- When a user can do something or see data of another user with the same level of permissions.

Vertical Privilege Escalation:
- When a user can do something or see data of another user with higher permissions.

<p align="center"> <img src="https://i.imgur.com/yRkU3uk.png" height="90%" width="90%" alt=""/>

<h2></h2>

Question #1: Access the administration page!

`946a799363226a24822008503f5d1324536629a0`

On the website's home page > Right click "Inspect" > Select "Sources" > Go to "main-es2015.js" > Press "ctrl + F" to search for `administration`.

<p align="center"> <img src="https://i.imgur.com/ieOn60j.png" height="90%" width="90%" alt=""/>

Found there is a path administration > navigate to that path by putting on the URL.

<p align="center"> <img src="https://i.imgur.com/DuWJnoz.png" height="90%" width="90%" alt=""/>

We will login admin account then try again > Successfully capture the flag.

<p align="center"> <img src="https://i.imgur.com/mWTcNpX.png" height="90%" width="90%" alt=""/>


<h2></h2>

Question #2: View another user's shopping basket!

`41b997a36cc33fbe4f0ba018474e19ae5ce52121`

Turn on Intercept with Burp Suite > Click on the basket icon on the top 

<p align="center"> <img src="https://i.imgur.com/djqfSNg.png" height="90%" width="90%" alt=""/>

Click on Forward > Burp Suite "GET" request will change

<p align="center"> <img src="https://i.imgur.com/0asKi4b.png" height="90%" width="90%" alt=""/>

Change "/basket/1" into `/basket/2` > Click Forward > Successfully captured the flag.

This changed to UserID 2's basket.

<p align="center"> <img src="https://i.imgur.com/jAU3aVi.png" height="90%" width="90%" alt=""/>

<h2></h2>

Question #3: Remove all 5-star reviews!

`50c97bcce0b895e446d61c83a21df371ac2266ef`

Navigate to the `http://10.10.236.183/#/administration` page > Click the bin icon next to the review with 5 stars!

<p align="center"> <img src="https://i.imgur.com/SVrMBFk.png" height="90%" width="90%" alt=""/>

Successfully capture the flag.

<p align="center"> <img src="https://i.imgur.com/ZjNA4lq.png" height="90%" width="90%" alt=""/>

<h2></h2>

# Where did that come from?

<h3>Cross-Site Scripting XSS</h3>

<p align="center"> <img src="https://i.imgur.com/unMzrgj.png" height="90%" width="90%" alt=""/>

Simplified Explanation of XSS (Cross-site Scripting):

XSS, or Cross-site scripting, is a security problem that allows bad actors to run JavaScript in web applications. These issues are quite common in web apps and can be easy or really tricky to fix because each app handles queries differently.

Three Main Types of XSS Attacks:

- DOM XSS (Special):

  - Uses the HTML environment to run harmful JavaScript.
  - Often involves the <script></script> HTML tag.
  
- Persistent XSS (Server-side):

  - JavaScript runs when the server loads a page.
  - Happens when the server doesn't properly clean up user data before displaying it on a page.
  - Frequently seen in blog posts.

- Reflected XSS (Client-side):

  - JavaScript runs on the user's side of the web app.
  - Often occurs when the server doesn't properly clean search data.
 
In simpler terms, XSS is like a sneaky way bad actors use to make a website do things it shouldn't, and there are different types depending on where the tricky code shows up.

<h2></h2>

Question #1: Perform a DOM XSS!

`9aaf4bbea5c30d00a1f5bbcfce4db6d4b0efe0bf`

We will be using the iframe element with a javascript alert tag: <iframe src="javascript:alert(`xss`)"> 

Inputting this into the search bar will trigger the alert.

<p align="center"> <img src="https://i.imgur.com/fLfMQkz.png" height="90%" width="90%" alt=""/>

Keep in mind that we're using an "iframe," which is a common building block in web applications. There are similar elements that achieve the same outcome.

This kind of XSS is known as XFS, or Cross-Frame Scripting. It's a common way to identify XSS in web applications.

If a website lets users change the iframe or other parts of the webpage (DOM elements), it's probably at risk for XSS.

Why does this work?

It is common practice that the search bar will send a request to the server in which it will then send back the related information, but this is where the flaw lies. Without correct input sanitation, we are able to perform an XSS attack against the search bar. 

Successfully captured the flag.

<p align="center"> <img src="https://i.imgur.com/dtEXGIt.png" height="90%" width="90%" alt=""/>

<h2></h2>

Question #2: Perform a persistent XSS!

`149aa8ce13d7a4a8a931472308e269c94dc5f156`

Log out > Login to the admin account to refresh the cache.

Turn on interception on Burp Suite > Log out.

<p align="center"> <img src="https://i.imgur.com/g0AqzRx.png" height="90%" width="90%" alt=""/>

Click on "+" > Name: "True-Client-IP" > Value: "<iframe src="javascript:alert(`xss`)">" > Add > Forward

<p align="center"> <img src="https://i.imgur.com/acBSSdH.png" height="90%" width="90%" alt=""/>

Turn off interception on Burp Suite > Refresh the webpage. Successfully captured the flag.

<p align="center"> <img src="https://i.imgur.com/Xbn7O2M.png" height="90%" width="90%" alt=""/>

<h2></h2>

Question #3: Perform a reflected XSS!

`23cefee1527bde039295b2616eeb29e1edc660a0`

Login the admin account > Click on the three line on the top left corner > Click on "Order & Payment" > Select "Order History".

<p align="center"> <img src="https://i.imgur.com/WsFdowo.png" height="90%" width="90%" alt=""/>

From there you will see a "Truck" icon, clicking on that will bring you to the track result page. You will also see that there is an id paired with the order.   

`http://10.10.236.183/#/track-result?id=5267-11d7516875e64656`

We will replace `5267-11d7516875e64656` with "<iframe src="javascript:alert(`xss`)">"

<p align="center"> <img src="https://i.imgur.com/NDK0x8m.png" height="90%" width="90%" alt=""/>

After submitting the URL, refresh the page and you will then get an alert saying XSS!

<p align="center"> <img src="https://i.imgur.com/IVKrW1L.png" height="90%" width="90%" alt=""/>

Successfully captured the flag.

<p align="center"> <img src="https://i.imgur.com/butPQFt.png" height="90%" width="90%" alt=""/>

Why does this work?

The server will have a lookup table or database (depending on the type of server) for each tracking ID. As the 'id' parameter is not sanitised before it is sent to the server, we are able to perform an XSS attack.  



