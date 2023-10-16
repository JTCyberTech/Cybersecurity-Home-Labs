# Prerequisites

- Create a free Azure account
- Download PuTTY (remote connection program) to access our VM

In this project, I have successfully implemented T-POT on the Azure Cloud infrastructure. T-POT, a sophisticated honeypot, emulates 23 distinct vulnerable systems. This project has helped me gain valuable insights into Linux configuration and network settings within a cloud environment, augmenting my technical proficiency. Furthermore, it has enriched my skill set in threat detection, acquired through vigilant monitoring and in-depth analysis of honeypot-generated data. This hands-on experience provided me with firsthand exposure to the methodologies employed by threat actors as they seek to exploit various vulnerabilities and compromise system security.

<h2></h2>

<h2>Creating an Azure Account</h2>

- Sign in or create a new account for [Azure Trial](https://azure.microsoft.com/en-us/free/).
    - You will have to put in your credit card information to get the trial subscription with $200 free credits.


- After the subscription is created, head to [Azure Portal](https://portal.azure.com) and select the account that has been associated with the trial subscription.

<h2></h2>

<h2>Downloading PuTTY</h2>

- Navigate to PuTTY download site by searching PuTTY download on Google or Click [Here](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)

- To know which version should be download, you go to command prompt and type in: Systeminfo

- See what is the System Type

<p align="center">
CMD System Type <br/>
<img src="https://i.imgur.com/lVwEDfu.png" height="60%" width="60%" alt=""/>
<br />

- Click the version under MSI (Windows Installer)

<p align="center">
<br/>
<img src="https://i.imgur.com/pEj49Z9.png" height="60%" width="60%" alt=""/>
<br />

<h2></h2>

Here are the steps I will be taking to complete this project:

1. Create VM in Azure for Honeypot

2. Installation and Configuration of Honeypot in Azure

3. Honeypot Web Interface

4. Discover Threats with HoneyPot in Real-Time

