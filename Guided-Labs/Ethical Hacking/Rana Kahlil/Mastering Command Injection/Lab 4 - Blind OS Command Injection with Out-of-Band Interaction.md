# Lab 4 - Blind OS Command Injection with Out-of-Band Interaction

<h2>Lab 4: Setup</h2>

<h3>Burp Suite Startup</h3>

- Open up Burp Suite by clicking on the Kali Linux icon on the left upper corner to expand the menu.
  - Type in: "Burp Suite" on the search bar.

<p align="center">
<br/>
<img src="https://i.imgur.com/GBtG9zI.png" height="90%" width="90%" alt=""/>
<br />

- Click on "OK".

<p align="center">
<br/>
<img src="https://i.imgur.com/930R9vx.png" height="60%" width="60%" alt=""/>
<br />

- Click on "I Accept".

<p align="center">
<br/>
<img src="https://i.imgur.com/sI08aew.png" height="60%" width="60%" alt=""/>
<br />

- Click on "Next".

<p align="center">
<br/>
<img src="https://i.imgur.com/mi2gE49.png" height="60%" width="60%" alt=""/>
<br />

- Click on "Start Burp".

<p align="center">
<br/>
<img src="https://i.imgur.com/u28bHJy.png" height="60%" width="60%" alt=""/>
<br />

<h2></h2>

<h3>Intercept Requests Using Burp Proxy</h3>

- Once Burp Suite finished loading, click on "Proxy".

<p align="center">
<br/>
<img src="https://i.imgur.com/TSszN7l.png" height="90%" width="90%" alt=""/>
<br />

- Click on "Open browser".

<h2></h2>

<h3>Navigate to Command Injection Labs in Portswigger On Burp Suite Browser</h3>

- Log in to [PortSwigger](https://portswigger.net/) Website.

- Click on the three line under "MY ACCOUNT" on PortSwigger Website. Then, click on "Academy".

<p align="center">
<br/>
<img src="https://i.imgur.com/bx2sfy8.png" height="90%" width="90%" alt=""/>
<br />

- Click on the expand button. Then, click on "Latest topics" and "View all topics".

<p align="center">
<br/>
<img src="https://i.imgur.com/QhgwDsX.png" height="90%" width="90%" alt=""/>
<br />

- Scroll down and click on "Command Injection".

<p align="center">
<br/>
<img src="https://i.imgur.com/SjhFwI3.png" height="90%" width="90%" alt=""/>
<br />

- Scroll down and click on the lab "Blind OS command injection with out-of-band interaction".

<p align="center">
<br/>
<img src="https://i.imgur.com/fzuslWK.png" height="90%" width="90%" alt=""/>
<br />

- Click on "ACCESS THE LAB".

<p align="center">
<br/>
<img src="https://i.imgur.com/OpU5vjY.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h2>Lab Description:</h2>

This lab contains a blind OS command injection vulnerability in the feedback function.

The application executes a shell command containing the user-supplied details. The command is executed asynchronously and has no effect on the application's response. It is not possible to redirect output into a location that you can access. However, you can trigger out-of-band interactions with an external domain.


<h2>Lab Solution</h2>

The target goal: Exploit blind OS command injection to issue a DNS lookup to Burp Collaborator.

Analysis: "& nslookup zorh37nyfzjbsg1nog7j9ml6zx5ntc.burpcollaborator.net #".

- It is not possible to redirect output into a location that you can access.


<h2></h2>

- Navigate to Burp Suite turn Intercept On by clicking on "Intercept is off".

<p align="center">
<br/>
<img src="https://i.imgur.com/YzGDBNL.png" height="90%" width="90%" alt=""/>
<br />

- Navigate to the Intercept Browser, click on "Submit feedback".

<p align="center">
<br/>
<img src="https://i.imgur.com/UtNu6mG.png" height="90%" width="90%" alt=""/>
<br />

- Navigate back to Burp Suite turn Intercept On by clicking on "Intercept is on".

<p align="center">
<br/>
<img src="https://i.imgur.com/ysjlWSa.png" height="90%" width="90%" alt=""/>
<br />

- Navigate back to the Intercept Browser, fill in the "Submit feedback".
  - Name: "test".
  - Email: "test@test.ca".
  - Subject: "test".
  - Message: "test".
- Click on "Submit feedback".

<p align="center">
<br/>
<img src="https://i.imgur.com/t23Mf8B.png" height="90%" width="90%" alt=""/>
<br />
