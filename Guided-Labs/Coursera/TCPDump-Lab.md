# TCPDump Basic Commands Practice

<h2>Description</h2>

Tcpdump is a powerful and flexible command line utility specially designed for cybersecurity professionals. Its main purpose is to intercept and inspect network traffic passing through your system. With many options and filters, tcpdump is an indispensable aid in network troubleshooting and enhancing security measures. By leveraging tcpdump's capabilities, cybersecurity professionals can effectively monitor and analyze network communications in a variety of scenarios.

In this mini project I will be using TCPDump simple commands to capture newtwork traffic.

<h2>Environments Used </h2>

- <b>Kali Linux VM</b>
- <b>TCPDump</b>

<h2>How to Capture Network Traffic</h2>

1. Open Terminal on Kali Linux VM
2. Type on command line: 

        $ tcpdump

<p align="left">
Error message from Terminal: <br/>
<img src="https://i.imgur.com/qxc4m5C.png" height="70%" width="70%" alt=""/>
<br />
Since it said we don't have permission to perform this on device, we will use sudo [for superuser do, allows temporarily elevate.] 

3. Type on command line: 
  
       $ sudo tcpdump
  and enter your password
  
<p align="left">
Performing TCPDump using sudo: <br/>
<img src="https://i.imgur.com/opkUmpw.png" height="70%" width="70%" alt=""/>
<br />
  
4. TCPDump will capture traffic when you refresh a webpage.
  
<p align="left">
Capturing traffic with refreshed webpage: <br/>
<img src="https://i.imgur.com/zciKjLt.png" height="70%" width="70%" alt=""/>
<br />
Type: Ctrl + c to stop capture

<h2>Useful Tcpdump Commands</h2>
  
<h3>Capture Only 15 Packets</h3>  

Type on command line: 

        $ sudo tcpdump -c 15

<p align="left">
Capturing packets with refreshed webpage: <br/>
<img src="https://i.imgur.com/7wdVnbJ.png" height="70%" width="70%" alt=""/>
<br />
  Useful to test out if your network is up and running.
  
<h3>Capturing Packets with Number for Easier Visualization</h3>
  
Type on command line: 

       $ sudo tcpdump -c 15 -#

<p align="left">
Showing the number in each captured packet: <br/>
<img src="https://i.imgur.com/HLwLAH2.png" height="70%" width="70%" alt=""/>
<br />
  
<h3>Capture Packets in ASCII</h3>  

Type on command line: 

       $  sudo tcpdump -c 15 -#A

<p align="left">
Capturing packets in ASCII: <br/>
<img src="https://i.imgur.com/ZvI81j2.png" height="70%" width="70%" alt=""/>
<br />
character-encoding scheme format, encrypted
  
<h3>Capture Packets in HEX and ASCII</h3>  

Type on command line: 

      $ sudo tcpdump -c 15 -#XX

<p align="left">
Capturing packets in HEX and ASCII: <br/>
<img src="https://i.imgur.com/lN4gKt7.png" height="70%" width="70%" alt=""/>
<br />
  
<h3>Capture Packets in Readable Time Format</h3>  

Type on command line: 

      $ sudo tcpdump -c 15 -#tttt

<p align="left">
Capturing packets in Readable Time Format: <br/>
<img src="https://i.imgur.com/hQm3xAs.png" height="70%" width="70%" alt=""/>
<br />
  
<h3>List All Network Interfaces on Workstation</h3>  

Type on command line: 

      $ sudo tcpdump -D

<p align="left">
All Network Interfaces on Workstation: <br/>
<img src="https://i.imgur.com/jRbx4W0.png" height="70%" width="70%" alt=""/>
<br /> 
  
<h2>Capturing Network Traffic on Website</h2>

Capturing Network Traffic on Website
Type on command line: 

      $ sudo tcpdump -#tttt host offsec.com -c 5 
  
  
Capturing Network Traffic on port 443
Type on command line: 

      $ sudo tcpdump -#tttt -c 5 port 443

  
Capturing Network Traffic on port 443 and a website
Type on command line:

     $ sudo tcpdump -#tttt -c 5 port 443 and host offsec.com

<p align="left">
Capturing Network Traffic on a port and website: <br/>
<img src="https://i.imgur.com/SkS1ZEQ.png" height="70%" width="70%" alt=""/>
<br /> 
  host offsec.com capture both incoming and outogoing traffic.
  
Capture incoming traffic only : 
  
    $ sudo tcpdump -#tttt -c 5 port 443 and src offsec.com
  
Capture outgoing traffic only: 
  
    $ sudo tcpdump -#tttt -c 5 port 443 and dst offsec.com
