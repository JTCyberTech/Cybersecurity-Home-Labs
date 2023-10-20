# Mastering Command Injection

<h3>What is Command Injection?</h3>

- Command Injection is also known as OS Command Injection.

- A vulnerability that consists of an attacker executing commands on the host OS with a vulnerable application.

<h2></h2>

<h3>Example: A vulnerable web application with no server side validation and the web server is running the application. </h3>

How a Normal User will use the web application: [ping IP Address: ```127.0.0.1```]

- Use the web application to ping the IP address that they want to check if it's up and running.

- The ping will initiate a request to the web server and execute the ping command.

- The ping command send an ICMP echo request to the IP address device and if the device is up, it sends back an ICMP echo response.

- The response is outputted in the web application.


<p align="center">
<br/>
<img src="https://i.imgur.com/c1sv8Ep.png" height="90%" width="90%" alt=""/>
<br />

If a Malicious Attacker gain access to the web application: [ping IP Address with command injection: ```120.0.0.1 && cat /etc/passwd```]

- The attacker can run a "cat command" to output the contents of the /etc/passwd file.
  - /etc/passwd is a world readable file. Regardless of the user context in which the web application operates, it would have the capability to access the file in the event it is susceptible to command injection.

- The attacker ping the IP address with the command injection.

- The server sends back an ICMP echo response with both commands.

- Allowed the attacker to exfiltrate the information from the web application.

<p align="center">
<br/>
<img src="https://i.imgur.com/UIVIyoS.png" height="90%" width="90%" alt=""/>
<br />

- 
