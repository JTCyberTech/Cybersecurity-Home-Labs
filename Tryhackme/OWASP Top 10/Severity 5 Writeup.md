# Task 18  [Severity 5] Broken Access Control (IDOR Challenge)

Deploy the machine and go to http://MACHINE_IP - Login with the username being noot and the password test1234.

<p align="center">
<br/>
<img src="https://i.imgur.com/IoqgW0J.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

1. Look at other users notes. What is the flag?

- After logging into user account: noot.

<p align="center">
<br/>
<img src="https://i.imgur.com/C8qdFCS.png" height="90%" width="90%" alt=""/>
<br />

- Change the "note=1" on the URL to "note=0".

<p align="center">
<br/>
<img src="https://i.imgur.com/MGDaiLQ.png" height="90%" width="90%" alt=""/>
<br />

Answer: `flag{fivefourthree}`
