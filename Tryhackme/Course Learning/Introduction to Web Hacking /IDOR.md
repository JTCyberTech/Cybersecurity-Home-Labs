# What is IDOR

Learn about: 

- What an IDOR vulnerability is?
- What they look like?
- How to find them?
- Practical task exploiting real case scenario.

<h2></h2>

<h3>What is an IDOR?</h3>

IDOR = `Insecure Direct Object Reference`. A type of access control vulnerability.

- Vulnerability Type: Object retrieval vulnerability
- Trigger: User-supplied input for object retrieval (files, data, documents)
- Risk: Trusting input data without server-side validation
- Consequence: Unauthorized access to requested objects
- Solution: Implement server-side validation for user requests

<h2></h2>

<h3>Question: What does IDOR stand for?</h3>

Answer: `Inscure Director OBject Reference`


<h2></h2>

# An IDOR Example

For Example: 

- You sign up for an online service and click a link (http://online-service.thm/profile?user_id=1305) to view and edit your profile information.

- You change the user_id value to 1000 (http://online-service.thm/profile?user_id=1000) out of curiosity and find another user's information, revealing an IDOR vulnerability. A proper website should verify that the user requesting the data matches the user information being accessed.

<p align="center">
<br/>
<img src="https://i.imgur.com/rvByFWc.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Question: What is the Flag from the IDOR example website?</h3>

Answer: `THM{IDOR-VULN-FOUND}`


<h2></h2>

# Finding IDORs in Encoded IDs

<h3>Encoded IDs</h3>

- Data passing methods in web development: POST data, query strings, and cookies.
- Encoding is crucial for data transmission to ensure the receiving server can understand it.
- Encoding converts binary data into an ASCII string (typically a-z, A-Z, 0-9, and = for padding).
- Base64 encoding is common on the web for this purpose.
- Tools like https://www.base64decode.org/ help decode strings, edit data, and re-encode it using https://www.base64encode.org/.
- Useful for testing if web response changes after data manipulation.

<p align="center">
<br/>
<img src="https://i.imgur.com/ogUFdqt.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Question: What is a common type of encoding used by websites?</h3>

Answer: `Base64`


<h2></h2>

# Finding IDORs in Hashed IDs

<h3>Hashed IDs</h3>

- Hashed IDs can be more complex to work with compared to encoded IDs.
- Hashed IDs may follow a predictable pattern, like being the result of hashing an integer value.
- For instance, the ID "123" might become "202cb962ac59075b964b07152d234b70" when using MD5 hashing.
- Consider using a web service like https://crackstation.net/ to check discovered hashes. It has a vast database of hash-to-value results.
- This can help identify if there are any matches for the provided hashes.

<h2></h2>

<h3>Question: What is a common algorithm used for hashing IDs?</h3>

Answer: `md5`


<h2></h2>

# Finding IDORs in Unpredictable IDs

<h3>Unpredictable IDs</h3>

- In cases where conventional methods for detecting Insecure Direct Object Reference (IDOR) vulnerabilities fail, consider an alternative approach.
- To identify potential IDOR issues, create two separate user accounts on the platform or application in question.
- Swap the ID numbers between the two accounts and attempt to access each other's content.
- If you can view the content of another user using their swapped ID while logged in with a different account or even when not logged in, it indicates a valid IDOR vulnerability.

<h2></h2>

<h3>What is the minimum number of accounts you need to create to check for IDORs between accounts?</h3>

Answer: `2`


<h2></h2>

# Where are IDORs located

<h3>Where are they located?</h3>

- Vulnerable endpoints may not be visible in the address bar.
- They could be loaded via AJAX requests.
- Vulnerabilities may also be referenced in JavaScript files.

<h2></h2>

- Beware of unreferenced parameters in production endpoints.
- Unreferenced parameters may have been useful during development.
- Examine endpoints for potential security vulnerabilities, like parameter mining.
- Parameter mining can exploit unreferenced parameters to access unauthorized data.


<h2></h2>

# A Practical IDOR Example

Website for this IDOR Example: https://10-10-208-209.p.thmlabs.com

- Navigate to the Example website.

<p align="center">
<br/>
<img src="https://i.imgur.com/w8E6v8D.png" height="90%" width="90%" alt=""/>
<br />

- Go to the "Customer" tab and create an account to login.

<p align="center">
<br/>
<img src="https://i.imgur.com/MYZXMxS.png" height="90%" width="90%" alt=""/>
<br />

- Click on the "Your Account" tab.
  - The Your Account section allows you to update your username, email, and password.
  - Your username and email fields are pre-filled with your info.

<p align="center">
<br/>
<img src="https://i.imgur.com/TrhQS6C.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

We'll start by investigating how this information gets pre-filled. 

- Open the browser developer tool by Right-click the page and select "Inspect".

<p align="center">
<br/>
<img src="https://i.imgur.com/3VNSR8J.png" height="90%" width="90%" alt=""/>
<br />

- Select the network tab, and refresh the page.
  - An endpoint with the path `/api/v1/customer?id={user_id}`
 
<p align="center">
<br/>
<img src="https://i.imgur.com/JvL60xI.png" height="90%" width="90%" alt=""/>
<br />

- JSON format response includes user id, username, and email address. User information is derived from the id parameter in the query string.

<p align="center">
<br/>
<img src="https://i.imgur.com/am4eJMG.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Question 1: What is the username for user id 1?

You can try testing this id parameter for an IDOR vulnerability by changing the id to another user's id. Try selecting users with IDs 1 and 3 and then answer the questions below.

- Right-click on the line, select "Edit and Resend".

<p align="center">
<br/>
<img src="https://i.imgur.com/SEnovoZ.png" height="90%" width="90%" alt=""/>
<br />

- Change the id parameter to `1`. Then click "Send".

<p align="center">
<br/>
<img src="https://i.imgur.com/T4xqSQr.png" height="90%" width="90%" alt=""/>
<br />

Answer: `adam84`

<h2></h2>

Question 2: What is the email address for user id 3?

- Change the id parameter to `3`. Then click "Send".

<p align="center">
<br/>
<img src="https://i.imgur.com/Zj3JJV1.png" height="90%" width="90%" alt=""/>
<br />

Answer: `j@fakemail.thm`
