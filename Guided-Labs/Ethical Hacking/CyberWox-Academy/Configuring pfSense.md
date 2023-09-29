# Implementing pfSense Firewall for Network Segmentation and Enhanced Security

PfSense will be meticulously configured as a robust firewall solution to establish network segmentation within our private homelab environment. Access to PfSense will be restricted solely to our designated Kali Linux machine for enhanced security.

<h2>Download and install pfSense to VMware Workstation</h2>

1. Download the ISO file for pfSense [Here](https://www.pfsense.org/download/)

2. Select Image To Download:
    - Architecture: AMD64 (64-bit)
    - Installer: DVD Image (ISO) Installer
    - Mirror: Austin, TX USA   #Closest area to you

3. Download and Unzip the file

4. Open VMware Workstation > home tab > click on Create a new Virtual Machine

5. Configuration for new virtual Machine
    - Typical (recommended)
    - Install disc image file (iso) and select the pfsense
    - Virtual machine name: pfsense
    - Leave 20 GB for maximum disk size
    - Customize Hardware
      - Memory > 2048 GB
      - Add 5 more Network Adapters [6 in total]
      - Configure each Network Adapter to their custom specific virtual network

<p align="left">
Adding 5 more Network Adapters to Hardware <br/>
<img src="https://i.imgur.com/cTtE2EV.png" height="40%" width="40%" alt=""/>
<br />

6. 
