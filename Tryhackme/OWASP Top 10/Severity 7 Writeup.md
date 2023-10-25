# Task 20  [Severity 7] Cross-site Scripting

Copy the IP from the of the active machine on Tryhackme and paste it into the attackbox browser.

<p align="center">
<br/>
<img src="https://i.imgur.com/CeUeX6o.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

1. Navigate to http://MACHINE_IP/ in your browser and click on the "Reflected XSS" tab on the navbar; craft a reflected XSS payload that will cause a popup saying "Hello".

- Navigate to the "Reflected XSS" page.

<p align="center">
<br/>
<img src="https://i.imgur.com/tQQmsDS.png" height="90%" width="90%" alt=""/>
<br />

- Popup's (<script>alert(“Hello World”)</script>) creates a message popup on users browser.

<p align="center">
<br/>
<img src="https://i.imgur.com/EMXbQ63.png" height="90%" width="90%" alt=""/>
<br />

- We just want "Hello" to popup, so we will delete the "World".
  - <script>alert(“Hello”)</script>.
  - Paste "<script>alert(“Hello”)</script>" on the Term from URL bar.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/Gr2BSc7.png" height="90%" width="90%" alt=""/>
<br />

- Successfully got the answer.

<p align="center">
<br/>
<img src="https://i.imgur.com/VDDy1An.png" height="90%" width="90%" alt=""/>
<br />


Answer: `ThereIsMoreToXSSThanYouThink`

<h2></h2>

2. On the same reflective page, craft a reflected XSS payload that will cause a popup with your machines IP address.

- Google: JavaScript: returns the domain name of the web host.
  - "window.location.hostname" return the IP address of your machine in JavaScript.

<p align="center">
<br/>
<img src="https://i.imgur.com/t6mE4Oj.png" height="90%" width="90%" alt=""/>
<br />

- Use: <script>alert(“window.location.hostname”)</script> in the URL.

<p align="center">
<br/>
<img src="https://i.imgur.com/15pD20d.png" height="90%" width="90%" alt=""/>
<br />

- Successfully got the answer.

<p align="center">
<br/>
<img src="https://i.imgur.com/0rheXnX.png" height="90%" width="90%" alt=""/>
<br />

Answer: `ReflectiveXss4TheWin`

<h2></h2>

3. Now navigate to http://MACHINE_IP/ in your browser and click on the "Stored XSS" tab on the navbar; make an account. Then add a comment and see if you can insert some of your own HTML.

- Navigate to the "Stored XSS" page. Create an account.

<p align="center">
<br/>
<img src="https://i.imgur.com/u4hjiiE.png" height="90%" width="90%" alt=""/>
<br />

- Navigate back to "Stored XSS". And add a comment.

<p align="center">
<br/>
<img src="https://i.imgur.com/90mAO6E.png" height="90%" width="90%" alt=""/>
<br />

- Insert HTML code by typing: <h1> Hello </h1>

<p align="center">
<br/>
<img src="https://i.imgur.com/ir4h5cd.png" height="90%" width="90%" alt=""/>
<br />

- Successfully got the answer.

<p align="center">
<br/>
<img src="https://i.imgur.com/afg2kW9.png" height="90%" width="90%" alt=""/>
<br />

Answer: `HTML_T4gs`

<h2></h2>

4. On the same page, create an alert popup box appear on the page with your document cookies.

- Insert Popup script with "document.cookies" without the "".
  - <script>alert(document.cookies)</script>

<p align="center">
<br/>
<img src="https://i.imgur.com/E4DqoxO.png" height="90%" width="90%" alt=""/>
<br />

- Successfully got the answer.

<p align="center">
<br/>
<img src="https://i.imgur.com/tsMhFFN.png" height="90%" width="90%" alt=""/>
<br />

Answer: `W3LL_D0N3_LVL2`

<h2></h2>

5. Change "XSS Playground" to "I am a hacker" by adding a comment and using Javascript.

- Click on the hint.

<p align="center">
<br/>
<img src="https://i.imgur.com/LsEVWO0.png" height="90%" width="90%" alt=""/>
<br />

- Copy "document.querySelector('#thm-title').textContent = 'Hey'".
  - Put it into the popup script: "<script>document.querySelector('#thm-title').textContent = 'Hey'</script>".
  - Change "Hey" into "I am a hacker": "<script>document.querySelector('#thm-title').textContent = 'I am a hacker'</script>".
  - Paste it in the comment.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/TQaustr.png" height="90%" width="90%" alt=""/>
<br />

- Answer appeared.

<p align="center">
<br/>
<img src="https://i.imgur.com/FwD8Sd3.png" height="90%" width="90%" alt=""/>
<br />

Answer: `websites_can_be_easily_defaced_with_xss`
