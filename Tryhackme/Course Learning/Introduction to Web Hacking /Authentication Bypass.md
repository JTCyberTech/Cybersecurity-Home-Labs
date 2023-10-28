# Brief

Will learn about different ways website authentication methods can be:

- Bypassed
- Defeated
- Broken

These vulnerabilities can be some of the most critical as it often ends in leaks of customers personal data.

<h2></h2>

# Username Enumeration

A helpful exercise to complete when trying to find authentication vulnerabilities is creating a list of valid usernames.

Website error messages are great resources for collating this information to build our list of valid usernames.

We can download fuff on "https://github.com/ffuf/ffuf"/

<h2></h2>

Question 1: What is the username starting with si*** ?

- Navigate to the site that question asked with your VM: "http://10.10.163.26/customers/signup".
  - Entering "admin" as a username and fake information in other form fields triggers an error message: "An account with this username already exists."
  - This error message indicates the existence of valid usernames already registered in the system.
  - To identify these valid usernames, the ffuf tool is used, which checks against a list of commonly used usernames for potential matches.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/OgtJGBk.png" height="90%" width="90%" alt=""/>
<br />

- `ffuf -w /usr/share/wordlists/SecLists/Usernames/Names/names.txt -X POST -d "username=FUZZ&email=x&password=x&cpassword=x" -H "Content-Type: application/x-www-form-urlencoded" -u http://10.10.163.26/customers/signup -mr "username already exists"`
  - -w argument: selects the file's location on the computer that contains the list of usernames that we're going to check exists.
  - -X argument: specifies the request method, this will be a GET request by default, but it is a POST request in our example.
  - -d argument: specifies the data that we are going to send. In our example, we have the fields username, email, password and cpassword
  - We've set the value of the username to FUZZ. In the ffuf tool, the FUZZ keyword signifies where the contents from our wordlist will be inserted in the request.
  - -H argument is used for adding additional headers to the request.
  - We're setting the Content-Type to the webserver knows we are sending form data.
  - -u argument specifies the URL we are making the request to.
  - -mr argument is the text on the page we are looking for to validate we've found a valid username.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/UJ9V1Gs.png" height="90%" width="90%" alt=""/>
<br />

Answer: `simon`

Question 2: What is the username starting with st*** ?

Answer: `steve`

Question 3: What is the username starting with ro*** ?

Answer: `robert`


<h2></h2>

# Brute Force

- Brute force attack: An automated process.
- Commonly used passwords: Tested against usernames.
- Target: Single username or a list of usernames.

<h2></h2>

Question: What is the valid username and password (format: username/password)?

- Create a txt file name "valid_usernames.txt" that contents the usernames.
  - On Terminal, use the `vi` command:
    - `vi valid_usernames.txt`.
      - press `i` to insert words. And type in "simon steve robert" on seperate lines.
      - press `esc` and type in `:wq` to save.

<p align="center">
<br/>
<img src="https://i.imgur.com/4DEFXmm.png" height="90%" width="90%" alt=""/>
<br />

- Make sure you are in the same directory as the valid_usernames.txt
  - On Terminal use the ffuf command to attempt a brute force attack on the login page.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/UBkrHYX.png" height="90%" width="90%" alt=""/>
<br />

- `ffuf -w valid_usernames.txt:W1,/usr/share/wordlists/SecLists/Passwords/Common-Credentials/10-million-password-list-top-100.txt:W2 -X POST -d "username=W1&password=W2" -H "Content-Type: application/x-www-form-urlencoded" -u http://10.10.163.26/customers/login -fc 200`
  - Previously we used the FUZZ keyword to select where in the request the data from the wordlists would be inserted.
  - But because we're using multiple wordlists, we have to specify our own FUZZ keyword.
  - In this instance, we've chosen W1 for our list of valid usernames.
  - W2 for the list of passwords we will try.
  - The multiple wordlists are again specified with the -w argument but separated with a comma.
  - For a positive match, we're using the -fc argument to check for an HTTP status code other than 200.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/nO2qKW2.png" height="90%" width="90%" alt=""/>
<br />

Answer: `steve/thunder`


<h2></h2>

# Logic Flaw

<h3>What is a Logic Flaw?</h3>

- Authentication processes may have logic flaws.
- Logic flaws involve hackers bypassing, circumventing, or manipulating the typical logical path of an application.
- Logic flaws can be present in various parts of a website, but we're focusing on authentication examples.

<p align="center">
<br/>
<img src="https://i.imgur.com/WVSgIrU.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Logic Flaw Example</h3>

- Path checks: The code examines if the path the client is visiting starts with "/admin."
- Admin verification: If the path starts with "/admin," additional checks are performed to confirm the client's admin status.
- Access control: If the path doesn't begin with "/admin," the page is displayed to the client without additional admin checks.

<p align="center">
<br/>
<img src="https://i.imgur.com/yWL6SGy.png" height="90%" width="90%" alt=""/>
<br />

- The PHP code example uses "===" to ensure an exact match, including letter casing.
- There is a logic flaw in the code where unauthenticated users can bypass authentication checks.
- Unauthenticated users requesting "/adMin" can access the page without privilege checks.

<h2></h2>

<h3>Logic Flaw Practical</h3>

- We're going to examine the Reset Password function of the Acme IT Support website (http://10.10.163.26/customers/reset).
  - We see a form asking for the email address associated with the account on which we wish to perform the password reset.
  - If an invalid email is entered, you'll receive the error message "Account not found from supplied email address".

<p align="center">
<br/>
<img src="https://i.imgur.com/OPlJaMi.png" height="90%" width="90%" alt=""/>
<br />

- Email address "robert@acmeitsupport.thm" is accepted for demonstration.
  - The next stage of the form requires entering the associated username.
  - Entering "robert" as the username and clicking "Check Username" triggers a password reset email confirmation.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/zG3zlcr.png" height="90%" width="90%" alt=""/>
<br />

You may be wondering what the vulnerability could be in this application:
  
  - you have to know both the email and username
  - Then the password link is sent to the email address of the account owner.

This will require: running two `Curl Requests`

In the second step of the reset email process, the username is submitted in a POST field to the web server, and the email address is sent in the query string request as a GET field.

<h2></h2>

<h3>Curl Request 1:</h3>

`curl 'http://10.10.163.26/customers/reset?email=robert%40acmeitsupport.thm' -H 'Content-Type: application/x-www-form-urlencoded' -d 'username=robert'`

- Use the -H flag to add an additional header to the request.
- Set Content-Type to application/x-www-form-urlencoded to inform the web server about the data type being sent.
- Retrieve the user account from the query string in the application.
- Send the password reset email using data from the PHP variable $_REQUEST.
- The $_REQUEST variable in PHP contains data from both the query string and POST data.
- If the same key name is used in both query string and POST data, the application favors POST data.
- You can control where the password reset email is delivered by adding another parameter to the POST form.

<h2></h2>

<h3>Curl Request 2:</h3>

`curl 'http://10.10.163.26/customers/reset?email=robert@acmeitsupport.thm' -H 'Content-Type: application/x-www-form-urlencoded' -d 'username=robert&email={username}@customer.acmeitsupport.thm'`

- Create an account on Acme IT support customer section.
- This account gives you a unique email address: {username}@customer.acmeitsupport.thm.
- Use this email address to create support tickets.
- Rerun Curl Request 2 with your @acmeitsupport.thm email to create a ticket on your account.
- The ticket contains a link to log in as "Robert."
- Using Robert's account, you can access support tickets and find a flag.

<h2></h2>

Question: What is the flag from Robert's support ticket?

- Create a new account on the Acme website.

<p align="center">
<br/>
<img src="https://i.imgur.com/kjqzMz3.png" height="90%" width="90%" alt=""/>
<br />

- On Terminal put in the first curl Request.
  - `curl 'http://10.10.163.26/customers/reset?email=robert%40acmeitsupport.thm' -H 'Content-Type: application/x-www-form-urlencoded' -d 'username=robert'`
 
- On Terminal put in the second curl Request but with the email that you just created.
  - `curl 'http://10.10.163.26/customers/reset?email=robertmeitsupport.thm' -H 'Content-Type: application/x-www-form-urlencoded' -d 'username=robert&email=jeff@customer.acmeitsupport.thm'`

<p align="center">
<br/>
<img src="https://i.imgur.com/ZI0RwEB.png" height="90%" width="90%" alt=""/>
<br />

- Go on the Acme website with your account logged in. Go to the "Support Tickets" tab.
  - Click on the "Id" of the support Ticket.

<p align="center">
<br/>
<img src="https://i.imgur.com/YNHHBuu.png" height="90%" width="90%" alt=""/>
<br />

- Navigate to the link that is provided in the "Ticket Contenst":
  - `http://10.10.163.26/customers/reset/b88b163d2f6e45fb663725b71be276c8`

<p align="center">
<br/>
<img src="https://i.imgur.com/XwKpWxm.png" height="90%" width="90%" alt=""/>
<br />
 
- Logged into "Robert".

<p align="center">
<br/>
<img src="https://i.imgur.com/ZQOD4Ej.png" height="90%" width="90%" alt=""/>
<br />

- Navigate to the Support Tickets Contents to achieve the flag.

<p align="center">
<br/>
<img src="https://i.imgur.com/eKmYPpF.png" height="90%" width="90%" alt=""/>
<br />

Answer: `THM{AUTH_BYPASS_COMPLETE}`


<h2></h2>

# Cookie Tampering

<h3>Plain Text</h3>

The contents of some cookies can be in plain text, and it is obvious what they do.

For example, if these were the cookie set after a successful login:

- Set-Cookie: logged_in=true; Max-Age=3600; Path=/
- Set-Cookie: admin=false; Max-Age=3600; Path=/

We see one cookie (logged_in), which appears to control whether the user is currently logged in or not, another (admin), which controls whether the visitor has admin privileges.

Using this logic, if we were to change the contents of the cookies and make a request we'll be able to change our privileges.

<h2></h2>

<h3>Curl Request 1:</h3>

`curl http://10.10.163.26/cookie-test`

First, we'll start just by requesting the target page:

<p align="center">
<br/>
<img src="https://i.imgur.com/jbjrt2e.png" height="90%" width="90%" alt=""/>
<br />

- Returned a message of: Not Logged In.

<h2></h2>

<h3>Curl Request 2:</h3>

`curl -H "Cookie: logged_in=true; admin=false" http://10.10.163.26/cookie-test`

Now we'll send another request with the logged_in cookie set to true and the admin cookie set to false:

<p align="center">
<br/>
<img src="https://i.imgur.com/iOodBY3.png" height="90%" width="90%" alt=""/>
<br />

- We are given the message: Logged In As A User.

<h2></h2>

<h3>Curl Request 3:</h3>

`curl -H "Cookie: logged_in=true; admin=true" http://10.10.163.26/cookie-test`

Finally, we'll send one last request setting both the logged_in and admin cookie to true:

<p align="center">
<br/>
<img src="https://i.imgur.com/u0575ea.png" height="90%" width="90%" alt=""/>
<br />

- Result: Logged In As An Admin.

<h2></h2>

<h3>Hashing</h3>

- Sometimes cookie values can look like a long string of random characters.
- Called hashes which are an irreversible representation of the original text.

<p align="center">
<br/>
<img src="https://i.imgur.com/bn5g8CW.png" height="90%" width="90%" alt=""/>
<br />

- Hash output varies with different hash methods. Hashes are irreversible.
- Consistent hash output aids in database lookups.
- Services like crackstation.net store hashes and original strings.

<h2></h2>

<h3>Encoding</h3>

- Encoding resembles hashing but is reversible, unlike hashing.
- The purpose of encoding is to convert binary data into human-readable text.
- Encoded data is easily and safely transmitted over mediums that support only plain text ASCII characters.

Common encoding types:
- base32 which converts binary data to the characters A-Z and 2-7
- base64 which converts using the characters a-z, A-Z, 0-9,+, / and the equals sign for padding.

For Example: 
`Set-Cookie: session=eyJpZCI6MSwiYWRtaW4iOmZhbHNlfQ==; Max-Age=3600; Path=/`

- This string base64 decoded has the value of {"id":1,"admin": false} we can then encode this back to base64 encoded again but instead setting the admin value to true, which now gives us admin access.

<h2></h2>

Question 1: What is the flag from changing the plain text cookie values?

<p align="center">
<br/>
<img src="https://i.imgur.com/cjfLP2m.png" height="90%" width="90%" alt=""/>
<br />

Answer: `THM{COOKIE_TAMPERING}`

Question 2: What is the value of the md5 hash 3b2a1053e3270077456a79192070aa78?

- Navigate to https://crackstation.net/ and put in the hash value.

<p align="center">
<br/>
<img src="https://i.imgur.com/48OsiCB.png" height="90%" width="90%" alt=""/>
<br />

Answer: `463729`

Question 3: What is the base64 decoded value of VEhNe0JBU0U2NF9FTkNPRElOR30=?

- Navigate to https://www.base64decode.org/ and put in the base64 decoded value.

<p align="center">
<br/>
<img src="https://i.imgur.com/owpZTr5.png" height="90%" width="90%" alt=""/>
<br />

Answer: `THM{BASE64_ENCODING}`

Question 4: Encode the following value using base64 {"id":1,"admin":true}

- Navigate to https://www.base64encode.org/ and put in the base64 encode value.

<p align="center">
<br/>
<img src="https://i.imgur.com/HTawd4U.png" height="90%" width="90%" alt=""/>
<br />

Answer: `eyJpZCI6MSwiYWRtaW4iOnRydWV9`
