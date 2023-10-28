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

- Click on the "Change Log" and we found a new path "/tmp.zip.
  - Add `/tmp.zip` to the URL and access the new webpage.

<p align="center">
<br/>
<img src="https://i.imgur.com/bS9k5kq.png" height="90%" width="90%" alt=""/>
<br />

- A new zip file will be downloaded.

<p align="center">
<br/>
<img src="https://i.imgur.com/dAi0p6x.png" height="90%" width="90%" alt=""/>
<br />

- Open the "flag.txt" in the zip file.
  - Got the answer for question 4.

<p align="center">
<br/>
<img src="https://i.imgur.com/5swswoi.png" height="90%" width="90%" alt=""/>
<br />

Answer: `THM{KEEP_YOUR_SOFTWARE_UPDATED}`

<h2></h2>

# Developer Tools - Inspector

<h3>Question: What is the flag behind the paywall?</h3>

- Navigate to the "News" page for the Acme IT website.
  - Click on the third News "⭐ 3 Tips for keeping your printer working"

<p align="center">
<br/>
<img src="https://i.imgur.com/J6tgH7b.png" height="90%" width="90%" alt=""/>
<br />

- A popup box will block the content.

<p align="center">
<br/>
<img src="https://i.imgur.com/MaXBoCd.png" height="90%" width="90%" alt=""/>
<br />

- Right-click the popup box and select "Inspect".

<p align="center">
<br/>
<img src="https://i.imgur.com/erAKYGI.png" height="90%" width="90%" alt=""/>
<br />

- There will be a section for "This Element".
  - Change `display: block;` to `display: none;`
  - Found the answer for the question.

<p align="center">
<br/>
<img src="https://i.imgur.com/aNC8PnQ.png" height="90%" width="90%" alt=""/>
<br />

Answer: `THM{NOT_SO_HIDDEN}`

<h2></h2>

# Developer Tools - Debugger

<h3>Question: What is the flag in the red box?</h3>

- Navigate to the "Contact" page for the Acme IT website.
  - You will notice when you refresh the page, there will be a red block that flashes for a second with contents on it.

<p align="center">
<br/>
<img src="https://i.imgur.com/MBb3Mpd.png" height="90%" width="90%" alt=""/>
<br />
 
- Right-click the page and select "Inspect". Then go to the Debugger tab.

<p align="center">
<br/>
<img src="https://i.imgur.com/2BHP8Ho.png" height="90%" width="90%" alt=""/>
<br />

- Click and expand the "assets" under "sources". Select "flash.min.js". Then click on the `{ }` at the bottom of the page.
  - `{ }` will make the make the .js file more readable.

<p align="center">
<br/>
<img src="https://i.imgur.com/2BHP8Ho.png" height="90%" width="90%" alt=""/>
<br />

- Scroll down and click on the "number" for `flash['remove']();`.

<p align="center">
<br/>
<img src="https://i.imgur.com/FxXEoon.png" height="90%" width="90%" alt=""/>
<br />

- Refresh the page after you click on the "number". (for me it was `108`)
  - Got the answer for the question.

<p align="center">
<br/>
<img src="https://i.imgur.com/wtkCEyx.png" height="90%" width="90%" alt=""/>
<br />

Answer: `THM{CATCH_ME_IF_YOU_CAN}`

<h2></h2>

# Developer Tools - Network 

<h3>Question: What is the flag shown on the contact-msg network request?</h3>

- Navigate to the "Contact" page for the Acme IT website.
  - Right-click and select "Inspect". Then go to the "Network" tab.

<p align="center">
<br/>
<img src="https://i.imgur.com/4QFxREj.png" height="90%" width="90%" alt=""/>
<br />
 
- Put random message on the "Contact Us" form. Then click on the "Send Message" button.

<p align="center">
<br/>
<img src="https://i.imgur.com/jIB4WN8.png" height="90%" width="90%" alt=""/>
<br />

- A New event will appear. Click on it.

<p align="center">
<br/>
<img src="https://i.imgur.com/mUBMEb0.png" height="90%" width="90%" alt=""/>
<br />

- Inside the event. There will be a URL. Copy and paste the URL to access to new webpage.
  - `https://10-10-203-66.p.thmlabs.com/contact-msg`

<p align="center">
<br/>
<img src="https://i.imgur.com/w5AP2mQ.png" height="90%" width="90%" alt=""/>
<br />

- Found the Answer to the question.

<p align="center">
<br/>
<img src="https://i.imgur.com/4BTrxSA.png" height="90%" width="90%" alt=""/>
<br />

Answer: `THM{GOT_AJAX_FLAG}`
