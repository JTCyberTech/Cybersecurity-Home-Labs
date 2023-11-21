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

What date was the email received? (answer format: M/DD/YY)

`6/10/20`

<p align="center"> <img src="https://i.imgur.com/9Q11u1d.png" height="90%" width="90%" alt=""/>

#

Who is the email from?

`Mr. James Jackson`

<p align="center"> <img src="https://i.imgur.com/KjN6iuY.png" height="90%" width="90%" alt=""/>

#

What is his email address?

`info@mutawamarine.com`

<p align="center"> <img src="https://i.imgur.com/1u8olhU.png" height="90%" width="90%" alt=""/>

#

What email address will receive a reply to this email? 

`info.mutawamarine@mail.com`

<p align="center"> <img src="https://i.imgur.com/MkWOLZS.png" height="90%" width="90%" alt=""/>

#

What is the Originating IP?

First we click on "More" > "View Source".

<p align="center"> <img src="https://i.imgur.com/zathhCE.png" height="90%" width="90%" alt=""/>

Scroll down a little.

`192.119.71.157`

<p align="center"> <img src="https://i.imgur.com/b8X7BZG.png" height="90%" width="90%" alt=""/>

#

Who is the owner of the Originating IP? (Do not include the "." in your answer.)

We will use https://lookup.icann.org/en/lookup to find the owner.

- Copy and paste the IP [192.119.71.157] on the website.

<p align="center"> <img src="https://i.imgur.com/VaM1Pr3.png" height="90%" width="90%" alt=""/>

Found the Registrant:

`Hostwinds LLC`

<p align="center"> <img src="https://i.imgur.com/kZ65OzF.png" height="90%" width="90%" alt=""/>


