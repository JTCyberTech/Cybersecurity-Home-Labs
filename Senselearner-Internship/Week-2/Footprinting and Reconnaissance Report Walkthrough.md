# Domain Information:

- Domain Name: senselearner.com
- IP Address: [162.250.126.19]
- Registrar: [GoDaddy]
- Registration Date: [2021-07-02]
- Expiry Date: [2025-07-02]
- Status: [Status, e.g., Active]

We can use the dig command to find the IP Address of senselearner.com: 
- Type in Kali Linux Terminal:
  
       dig senselearner.com
  
- result:  162.250.126.19

<p align="left">
Dig command <br/>
<img src="https://i.imgur.com/lQ3f8iS.png" height="30%" width="30%" alt=""/>
<br />

We can use the whois command to find the Registrar, Registration Date, and Expiry Date for senselearner.com:
- Type in Kali Linux Terminal:
  
      whois senselearner.com
  
- result: GoDaddy, 2021-07-02, 2025-07-02

<p align="left">
Whois command <br/>
<img src="https://i.imgur.com/DxFqfja.png" height="30%" width="30%" alt=""/>
<br />

We can use the ping command to check the status of senselearner.com if it's available:
- Type in Kali Linux Terminal:

      ping senselearner.com

  - result: Active because it's pinging back
 
<p align="left">
Ping command <br/>
<img src="https://i.imgur.com/GG9V3vI.png" height="30%" width="30%" alt=""/>
<br />

# DNS Footprinting:

We can use the dig command to find the DNS Footprinting:
- Type in Kali Linux Terminal:

      dig senselearner.com ANY

- result: Found A records, MX records, SOA records, and NS records.

<p align="left">
Dig command for DNS Footprinting <br/>
<img src="https://i.imgur.com/glK6sw2.png" height="30%" width="30%" alt=""/>
<br />

# Web Footprinting:

**We can identify the web server software by:**
- Going to senselearner.com on your browser
- Press f12 to show the developer tool
- Navigate to the network tab
- Refresh the page
- Click on senslearner.com within the developer tool
- Scroll down the header to find the server

Result: 
- Server: Litespeed
- X-Powered-by: PHP/7.4.33


<p align="left">
Developer Tool on Browser to find server software and version <br/>
<img src="https://i.imgur.com/5k28Qaf.png" height="30%" width="30%" alt=""/>
<br />

**Directory and File Structure**

**We can use the website [Wappalyzer](https://www.wappalyzer.com/lookup/senselearner.com/) to look up the technologies in use for Senselearner.**

<p align="left">
Wappalyzer Screenshot <br/>
<img src="https://i.imgur.com/gjg8W4s.png" height="30%" width="30%" alt=""/>
<br />

[Full Report](https://drive.google.com/file/d/1wmbcNYv7vAcfRwHm9NlTdqVhhYOGUqbs/view?usp=sharing)


**We can find the meta data for senselearner.com by:**
- Right-click on senselearner.com
- View page source
- Press Ctrl + F
- Search word: Meta

<p align="left">
Meta Data Search <br/>
<img src="https://i.imgur.com/NoX8rwF.png" height="30%" width="30%" alt=""/>
<br />
