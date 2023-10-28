# Walking An Application

Learn: 

- Manual web application security review
- Use in-built browser tools
- Automated tools may miss vulnerabilities
- Uncover potential vulnerabilities
- Gather useful information

 Short breakdown of the in-built browser tools you will use throughout this room:

 - View Source - Use your browser to view the human-readable source code of a website.
 - Inspector - Learn how to inspect page elements and make changes to view usually blocked content.
 - Debugger - Inspect and control the flow of a page's JavaScript
 - Network - See all the network requests a page makes.

<h2></h2>

# Exploring The Website

- Role of a penetration tester: Discover and assess potential vulnerabilities in a website or web application.
- Focus on interactive features: Vulnerabilities often exist in parts of the website that require user interaction.
- Methods for finding interactive portions:
  - Identifying login forms and other user input fields.
  - Reviewing the website's JavaScript for potential security issues.
- Start with browser exploration: Use your web browser to navigate the site and document individual pages, areas, and features with a summary for each.

An example site review for the Acme IT Support website would look something like this:

<p align="center">
<br/>
<img src="https://i.imgur.com/kHxDUC5.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

# Viewing The Page Source

<h3>Question 1: What is the flag from the HTML comment?</h3>

- Navigate to the webpage for Acme IT Support.

<p align="center">
<br/>
<img src="https://i.imgur.com/ACKfB5D.png" height="90%" width="90%" alt=""/>
<br />

- Right-click on the webpage, select "View Page Source".

<p align="center">
<br/>
<img src="https://i.imgur.com/LbpoDpc.png" height="90%" width="90%" alt=""/>
<br />

- Navigate to the new URL by adding `/new-home-beta` from the comment on the page source.
  - `https://10-10-203-66.p.thmlabs.com/new-home-beta`

<p align="center">
<br/>
<img src="https://i.imgur.com/fnzskWe.png" height="90%" width="90%" alt=""/>
<br />

- Got the first answer for HTML comment.

<p align="center">
<br/>
<img src="https://i.imgur.com/DCPkx4S.png" height="90%" width="90%" alt=""/>
<br />

Answer: `THM{HTML_COMMENTS_ARE_DANGEROUS}`

<h2></h2>

<h3>Question 2: What is the flag from the secret link?</h3>

- Navigate back to the "Page Source". There is a "secret page" with a link. Click on it.

<p align="center">
<br/>
<img src="https://i.imgur.com/WgiFWK4.png" height="90%" width="90%" alt=""/>
<br />

- Got the second answer for the secret link.

<p align="center">
<br/>
<img src="https://i.imgur.com/oZIzCfZ.png" height="90%" width="90%" alt=""/>
<br />

Answer: `THM{NOT_A_SECRET_ANYMORE}`

<h2></h2>

<h3>Question 3: What is the directory listing flag?</h3>

- Navigate back to the "Page Source". There seem to be another path called "/assets".

<p align="center">
<br/>
<img src="https://i.imgur.com/C9fqZy7.png" height="90%" width="90%" alt=""/>
<br />

- Add `/assets` to the URL and access the new webpage. On the new webpage, click on "flag.txt".
  - `https://10-10-203-66.p.thmlabs.com/assets`

<p align="center">
<br/>
<img src="https://i.imgur.com/UE6Zziq.png" height="90%" width="90%" alt=""/>
<br />
 
- Got the third answer from the "flag.txt".

<p align="center">
<br/>
<img src="https://i.imgur.com/wiLt1dF.png" height="90%" width="90%" alt=""/>
<br />

Answer: `THM{INVALID_DIRECTORY_PERMISSIONS}`

<h2></h2>

<h3>Question 4: What is the framework flag?</h3>

- Navigate back to the "Page Source". At the bottom, it said "THM Framework v1.2 ( https://static-labs.tryhackme.cloud/sites/thm-web-framework )"
  - Navigate to that webpage.

<p align="center">
<br/>
<img src="https://i.imgur.com/lJck6TQ.png" height="90%" width="90%" alt=""/>
<br />
 
- The Webpage said their current "version is 1.3". But the Acme website is still using version 1.2.

<p align="center">
<br/>
<img src="https://i.imgur.com/8bdyd9E.png" height="90%" width="90%" alt=""/>
<br />

- 
