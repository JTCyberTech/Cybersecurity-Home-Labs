# Virtual Network Configuration

<h2>Setting Up Two Networks</h2>

- Establishing a Private (Host-Only Network) on 10.0.3.x
  - Proactive security measure, effectively isolating our internal network from external internet threats
  - Safeguarding both our local network and the broader internet from potential vulnerabilities
    
- Establishing a Public (NAT Network) on 10.0.9.x
  - Provisioned to facilitate internet connectivity for essential tasks, including software updates and web browsing

<h2> </h2>

<h2>Creating Private Host-Only Network </h2>

1. Open up Oracle VM Application

2. Click on your Kali Linux VM to highlight Kali Linux VM

3. Click on File in top left corner > Host Network Manager or Ctrl + H

<p align="left">
Host Network Manager <br/>
<img src="https://i.imgur.com/3wRWC89.png" height="35%" width="35%" alt=""/>
<br />
   
4. Click on Create and change IPv4 Address: 10.0.3.2 for the Adapter Tab

<p align="left">
Adapter Tab <br/>
<img src="https://i.imgur.com/zopenfy.png" height="35%" width="35%" alt=""/>
<br />

5. Go to the DHCP Server Tab > Enable Server
  - Change Server Address: 10.0.3.3
  - Change Lower Address Bound: 10.0.3.4
  - Change Upper Address Bound: 10.0.3.100

<p align="left">
DHCP Server Tab <br/>
<img src="https://i.imgur.com/TlkcHBM.png" height="35%" width="35%" alt=""/>
<br />

6. Apply and Check the enable box for DHCP Server


 <h2> </h2>

 <h2>Creating Public NAT Network </h2>
