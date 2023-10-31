# What is an SSRF?

What this room teaches: 

- What an SSRF is.
- What kind of impact they can have.
- View some example SSRF attacks
- How you can discover SSRF vulnerabilities
- How to circumvent input rules
- Practice for you against with to try your newfound skills.

<h2></h2>

<h3>What is an SSRF?</h3>

Server-Side Request Forgery

- A vulnerability enabling a malicious user to manipulate the webserver to send a customized HTTP request to the attacker's target resource.

<h3>Types of SSRF</h3>

Two types of SSRF.

- Regular SSRF - where data is returned to the attacker's screen.
- Blind SSRF - vulnerability where an SSRF occurs, but no information is returned to the attacker's screen.

<h3>What's the impact?</h3>

A successful SSRF attack can result:

- Access to unauthorised areas.
- Access to customer/organisational data.
- Ability to Scale to internal networks.
- Reveal authentication tokens/credentials.

<h2></h2>

Question 1: What does SSRF stand for?

Answer: `Server Side Request Forgery`

Question 2: As opposed to a regular SSRF, what is the other type?

Answer: `Blind`


<h2></h2>

# SSRF Examples

<p align="center">
<br/>
<img src="https://i.imgur.com/A9C0P0J.png" height="90%" width="90%" alt=""/>
<br />


<p align="center">
<br/>
<img src="https://i.imgur.com/MUAXjLH.png" height="90%" width="90%" alt=""/>
<br />


<p align="center">
<br/>
<img src="https://i.imgur.com/z75nCrK.png" height="90%" width="90%" alt=""/>
<br />


<p align="center">
<br/>
<img src="https://i.imgur.com/zxcT0UJ.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Question: What is the flag from the SSRF Examples site?

- The hint said: "Append &x= at the end to ignore the rest of the URL."

- When we write on search bar, the server request is shown.
  - anything written after: `server=` will change.
 
- rewrite, `https://website.thm/item/2?server=api` into `https://website.thm/item/2?server=server.website.thm/flag?id=9&x=`

<p align="center">
<br/>
<img src="https://i.imgur.com/3GQYJhj.png" height="90%" width="90%" alt=""/>
<br />

Answer: `THM{SSRF_MASTER}`

<h2></h2>

# Finding an SSRF

Potential SSRF vulnerabilities can be spotted in web applications in many different ways. Here is an example of four common places to look:

<p align="center">
<br/>
<img src="https://i.imgur.com/PSgQPaP.png" height="90%" width="90%" alt=""/>
<br />

- Blind SSRF (Server-Side Request Forgery) may not provide immediate feedback.
- To monitor requests, use external HTTP logging tools like `requestbin.com`, your custom HTTP server, or Burp Suite's Collaborator client.

<h2></h2>

Question: What website can be used to catch HTTP requests from a server?

Answer: `requestbin.com`

<h2></h2>

# Defeating Common SSRF Defenses

- Security-savvy developers understand the risks of SSRF vulnerabilities.
- They implement checks in their applications to control resource requests.

Two common approaches are deny lists and allow lists:

<h3>Deny List:</h3>

- Deny List accepts all requests by default except those specified in the list or matching a particular pattern.
- It is used to protect sensitive resources, like endpoints, IP addresses, or domains, from public access while allowing access to other locations.
- Commonly used to restrict access to the localhost (e.g., localhost and 127.0.0.1) to safeguard server performance and sensitive information.
- Attackers can bypass a Deny List by using alternative localhost references or subdomains with DNS records pointing to 127.0.0.1.
- In a cloud environment, it's important to block access to the IP address `169.254.169.254` to protect sensitive cloud server metadata.
- Attackers can bypass this protection by registering a subdomain with a DNS record pointing to 169.254.169.254


<h3>Allow List:</h3>

- Allow List denies all requests by default and only permits those that match specified patterns or are on a predefined list.
- Used to enforce strict access control, like allowing only URLs beginning with a specific prefix (e.g., https://website.thm).
- Attackers can potentially circumvent an Allow List by creating subdomains on their domain that match the allowed pattern, enabling them to control internal HTTP requests.

<h2></h2>

<h3>Open Redirect</h3>

- When other bypass methods fail, attackers may resort to open redirects.
- An open redirect is a server endpoint that automatically redirects website visitors to another URL.
- In this context, an attacker could exploit an open redirect to redirect internal HTTP requests to a malicious domain of their choice.

<h2></h2>

Question 1: What method can be used to bypass strict rules?

Answer: `Open Direct`

Question 2: What IP address may contain sensitive data in a cloud environment?

Answer: `169.254.169.254`

Question 3: What type of list is used to permit only certain input?

Answer: `Allow List`

Question 4: What type of list is used to stop certain input?

Answer: `Deny List`


<h2></h2>

# SSRF Practical

Question: What is the flag from the /private directory?

- Create a customer account and sign in.

<p align="center">
<br/>
<img src="https://i.imgur.com/UexlRaP.png" height="90%" width="90%" alt=""/>
<br />

- Visit /customers/new-account-page to view new avatar selection.

<p align="center">
<br/>
<img src="https://i.imgur.com/ZtWnpwJ.png" height="90%" width="90%" alt=""/>
<br />

- Select an avatar then click on "Update Avatar".
  - View the page source will show your current avatar is displayed using the data URI scheme.

<p align="center">
<br/>
<img src="https://i.imgur.com/EdgJcJN.png" height="90%" width="90%" alt=""/>
<br />
 
- Try making the request again but changing the avatar value to private in hopes that the server will access the resource and get past the IP address block. To do this, firstly, right-click on one of the radio buttons on the avatar form and select Inspect:

<p align="center">
<br/>
<img src="https://i.imgur.com/YODfu9C.png" height="90%" width="90%" alt=""/>
<br />

- Change the value to "private". Then click on "Update Avatar".

<p align="center">
<br/>
<img src="https://i.imgur.com/TKJvpKk.png" height="90%" width="90%" alt=""/>
<br />

- The web application has a deny list in place and has blocked access to the /private endpoint.

<p align="center">
<br/>
<img src="https://i.imgur.com/Oigafi4.png" height="90%" width="90%" alt=""/>
<br />

- We will try again and change the value to "x/../private" instead.
  - It knows that the ../ string means to move up a directory that now translates the request to just /private.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/RDnjnfB.png" height="90%" width="90%" alt=""/>
<br />

- Right-click the blank avatar. Then click on "Inspect".
  - The base64 should be there.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/8tfPgzy.png" height="90%" width="90%" alt=""/>
<br />

- Go to the https://www.base64decode.org/
  - Put in the `VEhNe1lPVV9XT1JLRURfT1VUX1RIRV9TU1JGfQ==`
  - Decode it.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/59PBMa6.png" height="90%" width="90%" alt=""/>
<br />

Answer: `THM{YOU_WORKED_OUT_THE_SSRF}`
