# Home-Lab-VM

<h2>Description</h2>

A virtual machine (VM) such as VirtualBox can be utilized to establish a home lab dedicated to ethical hacking. This lab serves as a simulated real-world environment, providing users with a safe and secure space to enhance their ethical hacking skills. 

<h2>Environments Used </h2>

- <b>Windows 10</b>
- <b>Kali Linux VM</b>

<h2>Steps to set up a fundamental home lab of Kali Linux using VirtualBox:</h2>

<h3> How to Install VirtualBox</h3>

  1.  Download and install [VirtualBox](https://www.virtualbox.org/wiki/Downloads) with version that suits your Operating System]


(Since the latest version is a little bit buggy, I downloaded version 6.1)

<p align="left">
Downloading version 6.1 for Windows Operating System: <br/>
<img src="https://i.imgur.com/I2RYXTO.png" height="50%" width="50%" alt=""/>
<br />

2. If installed correctly, the VirtualBox will look like this:

  <p align="left">
Oracle VM VirtualBox: <br/>
<img src="https://i.imgur.com/y6a1DZk.png" height="60%" width="60%" alt=""/>
<br />
  
  
<h3> How to Configure VirtualBox</h3>

1. Click on Preferences on VirtualBox.
2. Click on Network and click on adds new NAT networks on the right side of the interface.
3. Double click on NatNetwork and rename it to LAB-NETWORK and put 10.10.10.0/24 on Network CIDR section and click OK.

<p align="left">
NAT Network Details: <br/>
<img src="https://i.imgur.com/bpFg75b.png" height="60%" width="60%" alt=""/>
<br />
  
  
<h3> How to Create Virutal Machines on Oracle VM VirtualBox (Kali Linux)</h3>

1. Download [Kali Linux](https://www.kali.org/get-kali/#kali-installer-images) with the version that suits your Operating System:
2. Create Virtual Machine on Oracle VM VirtualBox Manager by clicking on New

<p align="left">
Creating a New VM on VirtualBox: <br/>
<img src="https://i.imgur.com/v91sJUx.png" height="60%" width="60%" alt=""/>
<br />
  
  3. Name the new VM as Kali-VM and change <i>Type</i> to Linux and <i>Version</i> to Debian (64-bit) then click next.
  4. Change the Memory size to 2048 MB and click Next.
  5. Select: Create a virtual hard disk now.
  6. Select: VDI (VirtualBox Disk Image).
  7. Select: Dynamically allocated <i>for conserving Hard drive space</i>.
  8. Change the size to 40.00 GB.
  
<p align="left">
Kali-VM should be Created: <br/>
<img src="https://i.imgur.com/sHVgvaW.png" height="60%" width="60%" alt=""/>
<br />  
  
<h3> How to Configure Kali-VM on VirtualBox</h3>

1. Click on Settings 
2. Navigate to System tab and then Processor tab and change <i>Processor(s)</i> to 4 CPU
3. Navigate to display tab and change <i>Video Memory</i> to 32 MB and <i>Scale Factor</i> to 200%.

<p align="left">
Kali-VM Display Configuration: <br/>
<img src="https://i.imgur.com/OVzToDb.png" height="60%" width="60%" alt=""/>
<br /> 
  
  4. Navigate to Network tab and change <i>Attached to</i> NAT Network and <i>Name</i> to LAB-NETWORK
  
<p align="left">
Kali-VM Network Configuration: <br/>
<img src="https://i.imgur.com/tJuXRHf.png" height="60%" width="60%" alt=""/>
<br /> 
  
  5. Navigate to Storage tab and click on Empty under Controller: IDE and then click on the disk on the right side and select "choose a disk file" then locate Kali-Linux that was installed earlier.
  
<p align="left">
Kali-VM Storage Configuration: <br/>
<img src="https://i.imgur.com/18PxnA5.png" height="60%" width="60%" alt=""/>
<br /> 
  
  6. On Oracle VM VirtualBox Manager, select Kali-VM and click start.
  
<p align="left">
Kali-VM Should be Open: <br/>
<img src="https://i.imgur.com/ZAeWTRg.png" height="60%" width="60%" alt=""/>
<br />
  
  
<h3> How to Install Kali Linux Virtual Machine  </h3>

1. Click on graphical install and follow the instruction.
2. Create username that is not root or admin, and create a password.
3. Select: Guided - use entire disk.
4. Select: All files in one partition.
5. Select: Yes for Write the changes to disks
6. Keep everything default.
7. Select: Yes on install the GRUB boot loader
8. Select: /dev/sda (ata-VBOX_HARDDISK..) on the next page
9. Reboot and finished
10. Enter your user and password to login to Kali Linux VM

<p align="left">
Kali-VM Finished: <br/>
<img src="https://i.imgur.com/UX6kbTR.png" height="60%" width="60%" alt=""/>
<br />

# Advantages for Using a Virtual Home Lab:
  
  1. Versatility - By utilizing a home lab, an ethical hacker gains the advantage of tailoring the environment to their precise requirements. This heightened flexibility facilitates the exploration of various techniques and fosters the development of new skills with utmost convenience and effectiveness.
  2. Cost Efficiency: The utilization of a local virtual machine (VM) home lab for ethical hacking offers a significant advantage in terms of cost-effectiveness. Establishing and maintaining a home lab proves to be a more economical alternative compared to the procurement and upkeep of costly hardware and software solutions.
  3. Remote Accessibility: The local virtual machine (VM) home lab provides seamless access from any location with an internet connection, rendering it an optimal solution for individuals who frequently travel or work remotely from home.
  4. Expandability: The home lab possesses inherent scalability, enabling effortless expansion to accommodate additional machines or components as required. This inherent flexibility empowers ethical hackers to experiment with diverse techniques and technologies, fostering continuous exploration and advancement.
