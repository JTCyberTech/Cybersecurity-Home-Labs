# Project Requirements 

- Create an AWS Account
- Create Linux VM in VirtualBox
- Register Domain for ensure secure connections over HTTPS

We will create an AWS, Amazon Web Service, account to create a virtual machine to run our password manager.
We will create the Linux VM 
Domain registration provides a distinctive web address for your password management system, ensuring convenient accessibility for both yourself and authorized users.

It is option to skip creating a domain registration if you don't plan on using your password manager in the future.

<h2></h2>

<h2>Creating an AWS Account</h2>

Refer to [AWS Home Lab Part 1](https://github.com/jefftsui1/Cybersecurity-Home-Labs/blob/main/Guided-Labs/Ethical%20Hacking/AWS%20Home%20Lab/1.%20Sign%20Up%20for%20AWS%20and%20Enable%20MFA%20Security.md) for creating an AWS Account.

<h2></h2>

<h2>Downloading and Installing Linux VM in VirtualBox</h2>

Refer to [Vulnerability Scanner Deployment Project Part 2](https://github.com/jefftsui1/Cybersecurity-Home-Labs/blob/main/Guided-Labs/Ethical%20Hacking/Pavel%20Hrabec/Vulnerability%20Scanner%20Deployment/2.%20Installation%20of%20Windows%20on%20VirutalBox.md) for downloading VirtualBox.

- Navigate to the Ubuntu website for downloading Ubuntu 22.04.3 LTS [Here](https://ubuntu.com/download/desktop).
- Click on "Download 22.04.3"

<p align="center">
<br/>
<img src="https://i.imgur.com/pSODVyK.png" height="60%" width="60%" alt=""/>
<br />

- Once the download is complete, you should have an Ubuntu ISO file.

- Open VirtualBox and Click on New.

<p align="center">
<br/>
<img src="https://i.imgur.com/SIDn5DM.png" height="60%" width="60%" alt=""/>
<br />

- Under Name and Operating System:
  - Name the Virtual Machine, I will be naming it Kali Linux.
  - Select the Ubuntu ISO Image that we downloaded.

<p align="center">
<br/>
<img src="https://i.imgur.com/EsAcrsN.png" height="60%" width="60%" alt=""/>
<br />
 
- Under Unattended Install
  - Change Username: Admin.
  - Change to your own Password.
  - Change the Hostname: Linux.
  - Change Domain Name: linux.virtualbox.org.
  - Check the box for Guest Additions.
  - Find the VBoxGuestAdditions.iso in the folder you downloaded VirtualBox.
    - This will allow us to copy and paste between the VM and our environment.

<p align="center">
<br/>
<img src="https://i.imgur.com/o2f3zza.png" height="60%" width="60%" alt=""/>
<br />

- Under Hardware:
  - Base Memory: Put around 8000 MB. (Depends how powerful is your PC, you can put less)
  - Processor: Put 2 CPUs. (Depends how powerful is your PC, you can put less)
    - The more you put the faster the VM will be.

<p align="center">
<br/>
<img src="https://i.imgur.com/uOSKDwh.png" height="60%" width="60%" alt=""/>
<br />

- Under Hard Disk:
  - Should keep everything default, Size should be at least 25 GB but I will keep it as 50 GB. Then click on Finish
 
<p align="center">
<br/>
<img src="https://i.imgur.com/gC616si.png" height="60%" width="60%" alt=""/>
<br />
