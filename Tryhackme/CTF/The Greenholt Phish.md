# The Greenholt Phish

Room [The Greenholt Phish](https://tryhackme.com/room/phishingemails5fgjlzxc) on TryHackMe

#

# Introduction

A Sales Executive at Greenholt PLC received an email that he didn't expect to receive from a customer. He claims that the customer never uses generic greetings such as "Good day" and didn't expect any amount of money to be transferred to his account. The email also contains an attachment that he never requested. He forwarded the email to the SOC (Security Operations Center) department for further investigation. 

Investigate the email sample to determine if it is legitimate. 

# 

# Deploy the Machine

Deploy the machine attached to this task; it will be visible in the split-screen view once it is ready.

If you don't see a virtual machine automatically appear, click the Show Split View button.

Tip: Open the EML file with Thunderbird. To do so, right-click on the `challenge.eml` file and select Open With Other Application. From there, scroll down to select Thunderbird Mail and click Open. It may take a few moments to open the application. You will then see the email and its contents appear in the app.

<p align="center"> <img src="https://i.imgur.com/allH4HL.png" height="90%" width="90%" alt=""/>

#

# Questions

Question 1: What date was the email received? (answer format: M/DD/YY)

`6/10/20`

<p align="center"> <img src="https://i.imgur.com/9Q11u1d.png" height="90%" width="90%" alt=""/>

#

Question 2: Who is the email from?

`Mr. James Jackson`

<p align="center"> <img src="https://i.imgur.com/KjN6iuY.png" height="90%" width="90%" alt=""/>

#

Question 3: What is his email address?

`info@mutawamarine.com`

<p align="center"> <img src="https://i.imgur.com/1u8olhU.png" height="90%" width="90%" alt=""/>

#

Question 4: What email address will receive a reply to this email? 

`info.mutawamarine@mail.com`

<p align="center"> <img src="https://i.imgur.com/MkWOLZS.png" height="90%" width="90%" alt=""/>

#

Question 5: What is the Originating IP?

First we click on "More" > "View Source".

<p align="center"> <img src="https://i.imgur.com/zathhCE.png" height="90%" width="90%" alt=""/>

Scroll down a little.

`192.119.71.157`

<p align="center"> <img src="https://i.imgur.com/b8X7BZG.png" height="90%" width="90%" alt=""/>

#

Question 6: Who is the owner of the Originating IP? (Do not include the "." in your answer.)

We will use https://lookup.icann.org/en/lookup to find the owner.

- Copy and paste the IP [192.119.71.157] on the website.

<p align="center"> <img src="https://i.imgur.com/VaM1Pr3.png" height="90%" width="90%" alt=""/>

Found the Registrant:

`Hostwinds LLC`

<p align="center"> <img src="https://i.imgur.com/kZ65OzF.png" height="90%" width="90%" alt=""/>

#

Question 7: What is the SPF record for the Return-Path domain?

In order to find the SPF record, we have to use [https://dmarcian.com/domain-checker/].

In the source of our email, we will press "Ctrl + F" to search for return.
- Found the Return-Path domain to be "mutawamarine.com".

<p align="center"> <img src="https://i.imgur.com/JiLmcMv.png" height="90%" width="90%" alt=""/>

We will enter "mutawamarine.com" into "dmarcian.com".

<p align="center"> <img src="https://i.imgur.com/zO0Ouha.png" height="90%" width="90%" alt=""/>

From this search we found the SPF.

`v=spf1 include:spf.protection.outlook.com -all`

<p align="center"> <img src="https://i.imgur.com/RK8MaPs.png" height="90%" width="90%" alt=""/>

#

Question 8: What is the DMARC record for the Return-Path domain?

From the previous search we also found the DMARC record.

`v=DMARC1; p=quarantine; fo=1`

<p align="center"> <img src="https://i.imgur.com/aSP3rYc.png" height="90%" width="90%" alt=""/>

#

Question 9: What is the name of the attachment?

The Attachment name can be found at the bottom of the email.

`SWT_#09674321____PDF__.CAB`

<p align="center"> <img src="https://i.imgur.com/jWX4pYd.png" height="90%" width="90%" alt=""/>

#

Question 10: What is the SHA256 hash of the file attachment?

In order to find the SHA256 hash, we have to use Terminal.

`2e91c533615a9bb8929ac4bb76707b2444597ce063d84a4b33525e25074fff3f`

<p align="center"> <img src="https://i.imgur.com/8BdcAG4.png" height="90%" width="90%" alt=""/>

#

Question 11: What is the attachments file size? (Don't forget to add "KB" to your answer, NUM KB)

We will use Virustotal to search for the attachment file size. [https://www.virustotal.com/gui/home/search]

Put in the hash on search bar.

<p align="center"> <img src="https://i.imgur.com/bSw1K8I.png" height="90%" width="90%" alt=""/>

Found the size.

`400.26 KB`

<p align="center"> <img src="https://i.imgur.com/cO6LcXM.png" height="90%" width="90%" alt=""/>

#

Question 12: What is the actual file extension of the attachment?

`rar`

<p align="center"> <img src="https://i.imgur.com/CVZXIZ5.png" height="90%" width="90%" alt=""/>
