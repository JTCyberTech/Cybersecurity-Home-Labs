# Task 11  [Severity 3] Sensitive Data Exposure (Challenge)

Copy the IP from the of the active machine on Tryhackme and paste it into the attackbox browser.

<p align="center">
<br/>
<img src="https://i.imgur.com/7ZX95Tf.png" height="90%" width="90%" alt=""/>
<br />

1. What is the name of the mentioned directory?

Hint: Have a look at the source code on the /login page.

- Click on "Login"

<p align="center">
<br/>
<img src="https://i.imgur.com/HPpTGvy.png" height="90%" width="90%" alt=""/>
<br />

- Right-click on the login page and click on "View Page Source".

<p align="center">
<br/>
<img src="https://i.imgur.com/gKPJqpo.png" height="90%" width="90%" alt=""/>
<br />

- In the Page Source. Colored in green `/asset`.

<p align="center">
<br/>
<img src="https://i.imgur.com/lVqSwNB.png" height="90%" width="90%" alt=""/>
<br />

Answer: `/asset`


<h2></h2>

2. Navigate to the directory you found in question one. What file stands out as being likely to contain sensitive data?

- On the browser, navigate to the directory: "http://10.10.220.142/assets/".

<p align="center">
<br/>
<img src="https://i.imgur.com/pFUaLih.png" height="90%" width="90%" alt=""/>
<br />

- On the directory, "webapp.db" seems to be the flat-file database. Which is likely to contain sensitive data.

<p align="center">
<br/>
<img src="https://i.imgur.com/2XzLtkF.png" height="90%" width="90%" alt=""/>
<br />

Answer: `webapp.db`
