# Creating Linux VM on DigitalOcean

<h2>Description</h2>

DigitalOcean is a cloud provider known for its simplicity and cost-effective solutions, ideal for developers and businesses. They offer services like virtual machines, managed databases, and more, focusing on making cloud deployment and management easy. DigitalOcean's Linux-based services are user-friendly and affordable, while their 60-day, $200 credit program allows users to explore their cloud offerings without significant costs, making it an attractive choice for deploying and testing Linux-based applications and services.

<h2>Environments Used </h2>

- Linux

<h2></h2>

<h2>Creating Trial Account on DigitalOcean</h2>

- Navigate to [DigitalOcean](https://try.digitalocean.com/freetrialoffer/) Trial website.
  - Create a free account by clicking on "Create free account", via "Google", or "GitHub".
 
<p align="center">
<br/>
<img src="https://i.imgur.com/HQ2HAFb.png" height="90%" width="90%" alt=""/>
<br />

- Add in a payment method.

<p align="center">
<br/>
<img src="https://i.imgur.com/ULsv1W3.png" height="90%" width="90%" alt=""/>
<br />

- Afterward, free trial will applied to your account.

<p align="center">
<br/>
<img src="https://i.imgur.com/xViKbWU.png" height="60%" width="60%" alt=""/>
<br />

- Click on "Deploy a virtual machine".

<p align="center">
<br/>
<img src="https://i.imgur.com/uVpi8l5.png" height="90%" width="90%" alt=""/>
<br />

- Choose a region closest to you.

<p align="center">
<br/>
<img src="https://i.imgur.com/i4uPuHH.png" height="90%" width="90%" alt=""/>
<br />

- For Choose an image: "CentOS".
  - Version: "9 Stream x64".
  - Choose Size: "Basic".

<p align="center">
<br/>
<img src="https://i.imgur.com/STIMg9X.png" height="90%" width="90%" alt=""/>
<br />

- For CPU options: "Regular".
  - "$12/month, $0.018/hour. 2 GB/1 CPU"

<p align="center">
<br/>
<img src="https://i.imgur.com/9zLXDfd.png" height="90%" width="90%" alt=""/>
<br />
 
- For Choose Authentication Method: "Password".
  - Input your own password with the password requirement.

<p align="center">
<br/>
<img src="https://i.imgur.com/uVxvGYq.png" height="90%" width="90%" alt=""/>
<br />
 
- Scroll down, click on "Create Droplet".

<p align="center">
<br/>
<img src="https://i.imgur.com/p2TP3mT.png" height="90%" width="90%" alt=""/>
<br />
 
- Click on the droplet.

<p align="center">
<br/>
<img src="https://i.imgur.com/ElstQMn.png" height="90%" width="90%" alt=""/>
<br />
 
- The IPv4 address will be used to connect to the Linux machine.

<p align="center">
<br/>
<img src="https://i.imgur.com/AWbfOg7.png" height="90%" width="90%" alt=""/>
<br />


<h2></h2>

<h2>Using PuTTY to Connect</h2>

- Can use PuTTY. Tutorial on installing PuTTY [Here]().

- Paste the IP address to PuTTY.
  - Click on "Open".

<p align="center">
<br/>
<img src="https://i.imgur.com/jUEp46Y.png" height="60%" width="60%" alt=""/>
<br />

- Click on "Accept".

<p align="center">
<br/>
<img src="https://i.imgur.com/dZPUy1g.png" height="60%" width="60%" alt=""/>
<br />

- login as: "root".
- root@143.198.185.88's password: enter in the password that you made.

<p align="center">
<br/>
<img src="https://i.imgur.com/FAxhSA8.png" height="60%" width="60%" alt=""/>
<br />

Successfully login the Linux VM using PuTTY.
