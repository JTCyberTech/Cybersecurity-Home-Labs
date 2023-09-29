# Creating Ubuntu VM to Oracle VirtualBox

<h2>Description</h2>

Ubuntu is a feature-rich operating system with powerful functionality that is built for both desktop and server contexts. Kali Linux, on the other hand, acts as a specialized operating system that is especially designed for ethical hacking objectives. While Kali Linux focuses on providing a dedicated environment for digital forensics professionals, Ubuntu caters to the demands of developers and programmers by providing a flexible platform. In this lab I will show the steps that I took to download Ubuntu VM in Oracle VM VirtualBox.

<h2>Environments Used </h2>

- <b>Windows 10</b>
- <b>Ubuntu VM</b>

<h2> How to Create Virutal Machines on Oracle VM VirtualBox (Ubuntu)</h2>

 1. Download [Ubuntu](https://ubuntu.com/download/desktop) with the version that suits your Operating System:
 2. Create Virtual Machine on Oracle VM VirtualBox Manager by clicking on New

<p align="left">
Creating a New VM on VirtualBox: <br/>
<img src="https://i.imgur.com/Wck0JWo.png" height="60%" width="60%" alt=""/>
<br />
<p align="left">


 3. Name the new VM as Ubuntu-VM and change <i>Type</i> to Linux and <i>Version</i> to Ubuntu (64-bit) then click next.
  4. Change the Memory size to 2048 MB and click Next.
  5. Select: Create a virtual hard disk now.
  6. Select: VDI (VirtualBox Disk Image).
  7. Select: Dynamically allocated <i>for conserving Hard drive space</i>.
  8. Change the size to 40.00 GB.
  
<p align="left">
Ubuntu-VM should be Created: <br/>
<img src="https://i.imgur.com/xernwlz.png" height="60%" width="60%" alt=""/>
<br />  

<h3> How to Configure Ubuntu-VM on VirtualBox</h3>

1. Click on Settings 
2. Navigate to System tab and then Processor tab and change <i>Processor(s)</i> to 4 CPU
3. Navigate to display tab and change <i>Video Memory</i> to 64 MB and <i>Scale Factor</i> to 200%.

<p align="left">
Ubuntu-VM Display Configuration: <br/>
<img src="https://i.imgur.com/ecbbfc9.png" height="60%" width="60%" alt=""/>
<br /> 
  
  4. Navigate to Network tab and change <i>Attached to</i> NAT Network and <i>Name</i> to LAB-NETWORK
  
<p align="left">
Ubuntu-VM Network Configuration: <br/>
<img src="https://i.imgur.com/561imVL.png" height="60%" width="60%" alt=""/>
<br /> 
  
  5. Navigate to Storage tab and click on Empty under Controller: IDE and then click on the disk on the right side and select "choose a disk file" then locate Ubuntu version that was installed earlier.
  
<p align="left">
Ubuntu-VM Storage Configuration: <br/>
<img src="https://i.imgur.com/WFsxo1Q.png" height="60%" width="60%" alt=""/>
<br /> 
  
  6. On Oracle VM VirtualBox Manager, select Ubuntu-VM and click start.
  
<p align="left">
Ubuntu-VM Should be Open: <br/>
<img src="https://i.imgur.com/rKHOOjA.png" height="60%" width="60%" alt=""/>
<br />
  
  
<h3> How to Install Ubuntu Virtual Machine  </h3>

1. Click on Try or Install Ubuntu.
2. Install Ubuntu in English.
3. Updates and other software choose: Normall installation and uncheck Other options.
4. Installation type choose: Erase disk and install Ubuntu.
5. Choose your location
6. Who are you?: put your name and password.
7. Wait until it finish installing and restart

<p align="left">
Ubuntu-VM Finished: <br/>
<img src="https://i.imgur.com/1ILG4Mf.png" height="60%" width="60%" alt=""/>
<br />

  
# Advantages for Using a Virtual Home Lab:
  
  1. Versatility - By utilizing a home lab, an ethical hacker gains the advantage of tailoring the environment to their precise requirements. This heightened flexibility facilitates the exploration of various techniques and fosters the development of new skills with utmost convenience and effectiveness.
  2. Cost Efficiency: The utilization of a local virtual machine (VM) home lab for ethical hacking offers a significant advantage in terms of cost-effectiveness. Establishing and maintaining a home lab proves to be a more economical alternative compared to the procurement and upkeep of costly hardware and software solutions.
  3. Remote Accessibility: The local virtual machine (VM) home lab provides seamless access from any location with an internet connection, rendering it an optimal solution for individuals who frequently travel or work remotely from home.
  4. Expandability: The home lab possesses inherent scalability, enabling effortless expansion to accommodate additional machines or components as required. This inherent flexibility empowers ethical hackers to experiment with diverse techniques and technologies, fostering continuous exploration and advancement.
